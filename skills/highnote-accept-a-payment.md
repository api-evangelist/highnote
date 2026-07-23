---
name: Accept and capture an acquiring card payment
description: Authorize and capture (or single-step charge) an acquiring card payment on Highnote.
api: openapi/highnote-graphql-api-openapi.yml
endpoint: https://api.us.highnote.com/graphql
operations: [authorizePaymentCard, capturePaymentTransaction, chargePaymentCard]
---

# Accept a card payment (acquiring)

GraphQL mutations over HTTP Basic auth (base64 API key). Add an `IdempotencyKey` (v4 UUID) to
every mutation — critical for money movement to avoid double charges on retry.

## Auth + capture flow

1. **Authorize** — `authorizePaymentCard(input: AuthorizePaymentCardInput!)` with the payment
   card / payment method token and `MoneyInput` amount. Returns a `PaymentTransaction`. Listen for
   `CARD_PAYMENT_AUTHORIZED_EVENT` or `CARD_PAYMENT_AUTHORIZATION_DECLINED_EVENT`.
2. **Capture** — `capturePaymentTransaction(input: CapturePaymentTransactionInput!)` for the
   authorized transaction (full or partial; supports incremental/force capture). Watch
   `CARD_PAYMENT_CAPTURING_EVENT` → `CARD_PAYMENT_CLEARED_EVENT` → `CARD_PAYMENT_SETTLED_EVENT`.

## Single-step charge

- **Charge** — `chargePaymentCard(input: ChargePaymentCardInput!)` performs auth + capture in one
  call for card-not-present flows.

## Rules

- Collect card data with the `@highnoteplatform/checkout` or `@highnoteplatform/secure-inputs`
  iframe components so PCI data never crosses your server (SAQ-A).
- On decline, inspect the declined event and, in Test, reproduce with `cavvResultCode: FAILED`
  (Visa) / `aavResultCode: AAV_FAILED_VALIDATION` (Mastercard) for 3DS failures (sandbox/highnote-sandbox.yml).
- Errors-as-data: check the `UserError` union member; keep `extensions.requestId`.
