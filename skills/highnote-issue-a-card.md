---
name: Onboard an account holder and issue a payment card
description: Onboard a US person, apply to a card product, open a financial account, and issue + activate a payment card on Highnote.
api: openapi/highnote-graphql-api-openapi.yml
endpoint: https://api.us.highnote.com/graphql
operations: [createUSPersonAccountHolder, createAccountHolderCardProductApplication, issueFinancialAccountForApplication, issuePaymentCardForApplication, activatePaymentCard]
---

# Onboard and issue a card

All operations are GraphQL mutations sent as `POST` to the single endpoint. Authenticate with
HTTP Basic: base64-encode your API key and send `Authorization: Basic <base64(apiKey)>`. Add an
`IdempotencyKey` (v4 UUID) input to every mutation. Use the Test endpoint
`https://api.us.test.highnote.com/graphql` first.

## Steps

1. **Onboard the account holder** — `createUSPersonAccountHolder(input: CreateUSPersonAccountHolderInput!)`.
   Supply name, address, DOB, and identifiers for KYC. Capture the returned `id`.
2. **Apply to a card product** — `createAccountHolderCardProductApplication(input: CreateAccountHolderCardProductApplicationInput!)`
   with the account holder id and the target `cardProductId`. Watch for the
   `CARD_PRODUCT_APPLICATION_APPROVED` / `_DENIED` / `_MANUAL_REVIEW` webhook events.
   On denial, read `applicationDenialReason` (see errors/highnote-decline-codes.yml).
3. **Open a financial account** — after approval, `issueFinancialAccountForApplication(input: IssueFinancialAccountForApplicationInput!)`
   with the application id.
4. **Issue the card** — `issuePaymentCardForApplication(input: IssuePaymentCardForApplicationInput!)`
   choosing `formFactor` (VIRTUAL / PHYSICAL). Returns `bin`, `last4`, `expirationDate`, `network`, `status`.
5. **Activate** — `activatePaymentCard(input: ...)`. Confirm via the `PAYMENT_CARD_ACTIVATED` event.

## Rules

- Handle errors-as-data: check the mutation's `UserError` union member and the top-level `errors` array; log `extensions.requestId` for support.
- Never store PAN/CVV server-side — render cards with the `@highnoteplatform/card-viewer` component (packages/highnote-packages.yml) to stay in PCI SAQ-A scope.
- List queries use Relay pagination (`first`/`after`, `edges { node } pageInfo { endCursor hasNextPage }`).
