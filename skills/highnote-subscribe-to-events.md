---
name: Register a webhook target and subscribe to events
description: Register an HTTPS webhook notification target and subscribe it to Highnote event types.
api: openapi/highnote-graphql-api-openapi.yml
endpoint: https://api.us.highnote.com/graphql
operations: [addWebhookNotificationTarget, activateNotificationTarget, addSubscriptionsToNotificationTarget]
---

# Subscribe to Highnote events

GraphQL mutations over HTTP Basic auth. Prefer events over polling; events are retained 30 days
and queryable via the `notificationEvents` query.

## Steps

1. **Register the target** — `addWebhookNotificationTarget(input: AddWebhookNotificationTargetInput!)`
   with your HTTPS URL. Returns a `WebhookNotificationTarget`.
2. **Activate** — `activateNotificationTarget(input: ...)`. Highnote sends a
   `NOTIFICATION_ACTIVATION` and you can trigger `NOTIFICATION_PING_TEST` /
   `NOTIFICATION_EVENT_VALIDATION_TEST` to verify delivery.
3. **Subscribe to event types** — `addSubscriptionsToNotificationTarget(input: AddSubscriptionsToNotificationTargetInput!)`
   listing the event types you want (see asyncapi/highnote-events-asyncapi.yml for the catalog,
   e.g. `PAYMENT_CARD_ISSUED`, `CARD_PAYMENT_SETTLED_EVENT`, `ORIGINATED_ACH_TRANSFER_PROCESSED`).

## Rules

- Verify inbound deliveries (HMAC signature) before trusting them; deactivate with
  `deactivateNotificationTarget` to pause.
- Replay/monitor missed events via the `notificationEvents` query (filter by type/status/date).
- Reconcile idempotently — the same event may be delivered more than once.
