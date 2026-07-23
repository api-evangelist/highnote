---
name: Move funds across rails
description: Move funds between Highnote financial accounts or out over ACH, wire, RTP, or push-to-card.
api: openapi/highnote-graphql-api-openapi.yml
endpoint: https://api.us.highnote.com/graphql
operations: [initiateTransferBetweenFinancialAccounts, initiateAchTransfer, initiateUnifiedFundsTransfer]
---

# Move money

GraphQL mutations over HTTP Basic auth. **Always** supply a unique `IdempotencyKey` (v4 UUID) —
money movement is the highest-risk retry surface.

## Options

1. **On-us instant transfer** — `initiateTransferBetweenFinancialAccounts(input: InitiateTransferInput!)`
   moves funds between two Highnote financial accounts; on-us transfers settle instantly. Track
   `INTERNAL_TRANSFER_BETWEEN_FINANCIAL_ACCOUNTS_PENDING` → `_COMPLETED` / `_FAILED`.
2. **ACH** — `initiateAchTransfer(input: InitiateAchTransferInput!)` for standard or same-day ACH.
   Track `ORIGINATED_ACH_TRANSFER_INITIATED` → `_PROCESSING` → `_PROCESSED` / `_FAILED` / `_RETURNED`.
3. **Best-rail unified transfer** — `initiateUnifiedFundsTransfer(input: JSON!)` routes over ACH,
   wire, RTP, or push-to-card (Mastercard Move / Visa Direct) based on cost, speed, and destination.

## Rules

- Confirm balances first via `financialAccount { balances }`; over-limit/insufficient funds decline.
- Reconcile from webhook events, not polling (events retained 30 days; see asyncapi/highnote-events-asyncapi.yml).
- Errors-as-data: read the `UserError` union member; capture `extensions.requestId` for support.
