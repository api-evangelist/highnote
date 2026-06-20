# Highnote (highnote)

Highnote is a modern, unified embedded-finance platform for card issuing, acquiring, credit, and real-time money movement, with a built-in ledger and program management. The entire platform is driven by a single GraphQL API at https://api.us.highnote.com/graphql, authenticated with a base64-encoded API key over HTTP Basic auth, covering card products, account holders (persons and businesses), financial accounts, payment cards, transactions/authorizations, transfers, collaborative authorization, spend/velocity rules, and webhook notifications.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/highnote/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/highnote/refs/heads/main/apis.yml)

## Tags

- Card Issuing
- Embedded Finance
- Fintech
- Payments
- GraphQL
- Ledger
- Credit

## Timestamps

- **Created:** 2026-06-20
- **Modified:** 2026-06-20

## APIs

### Highnote Card Issuing API

Create and configure card products (createCardProduct), issue virtual, physical, and tokenized digital payment cards (issuePaymentCardForApplication, createPhysicalCardGroupOrder), activate and close cards, push-provision to Apple Pay / Google Pay, and attach spend and velocity rules. Driven through the single GraphQL endpoint with Basic auth.

- **Human URL:** [https://docs.highnote.com/docs/issuing/get-started-issuing/issuing-overview](https://docs.highnote.com/docs/issuing/get-started-issuing/issuing-overview)
- **Base URL:** `https://api.us.highnote.com/graphql`

#### Tags

- Card Products
- Payment Cards
- Virtual Cards
- Physical Cards
- GraphQL

#### Properties

- [Documentation](https://docs.highnote.com/docs/issuing/get-started-issuing/issuing-overview)
- [API Reference](https://docs.highnote.com/docs/api-reference/mutation)
- [GraphQL](graphql/highnote-graphql.md) — [GraphQL](https://spec.graphql.org)
- [OpenAPI](openapi/highnote-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/highnote.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/highnote.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Highnote Account Holders API

Onboard US person and US business account holders (createUSPersonAccountHolder, createUSBusinessAccountHolder), manage authorized users, submit and accept card product applications (createAccountHolderCardProductApplication), run KYC/KYB and identity-update flows, and query personAccountHolders / businessAccountHolders.

- **Human URL:** [https://docs.highnote.com/docs/api-reference/mutation](https://docs.highnote.com/docs/api-reference/mutation)
- **Base URL:** `https://api.us.highnote.com/graphql`

#### Tags

- Account Holders
- KYC
- KYB
- Applications
- GraphQL

#### Properties

- [Documentation](https://docs.highnote.com/docs/developers/api/using-the-api)
- [API Reference](https://docs.highnote.com/docs/api-reference/object)
- [GraphQL](graphql/highnote-graphql.md) — [GraphQL](https://spec.graphql.org)
- [OpenAPI](openapi/highnote-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/highnote.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/highnote.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Highnote Financial Accounts API

Issue financial accounts against approved applications (issueFinancialAccountForApplication), assign payment cards to financial accounts, manage credit limits and on-demand funding, and read balances and the real-time ledger via the FinancialAccount object and its account relationships.

- **Human URL:** [https://docs.highnote.com/docs/api-reference/object](https://docs.highnote.com/docs/api-reference/object)
- **Base URL:** `https://api.us.highnote.com/graphql`

#### Tags

- Financial Accounts
- Ledger
- Credit
- Balances
- GraphQL

#### Properties

- [Documentation](https://docs.highnote.com/docs/developers/api/using-the-api)
- [API Reference](https://docs.highnote.com/docs/api-reference/object)
- [GraphQL](graphql/highnote-graphql.md) — [GraphQL](https://spec.graphql.org)
- [OpenAPI](openapi/highnote-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/highnote.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/highnote.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Highnote Transactions API

Authorize, capture, charge, and cancel payment transactions (authorizePaymentCard, capturePaymentTransaction, chargePaymentCard), handle incremental and force captures, initiate cardholder transaction disputes, and query paymentTransactions and transactionBatches with HQL search.

- **Human URL:** [https://docs.highnote.com/docs/api-reference/query](https://docs.highnote.com/docs/api-reference/query)
- **Base URL:** `https://api.us.highnote.com/graphql`

#### Tags

- Authorizations
- Transactions
- Clearing
- Disputes
- GraphQL

#### Properties

- [Documentation](https://docs.highnote.com/docs/acquiring/about-acquiring)
- [API Reference](https://docs.highnote.com/docs/api-reference/object)
- [GraphQL](graphql/highnote-graphql.md) — [GraphQL](https://spec.graphql.org)
- [OpenAPI](openapi/highnote-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/highnote.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/highnote.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Highnote Transfers API

Move funds between financial accounts and external bank accounts via ACH, wire, and instant-payment rails (initiateTransferBetweenFinancialAccounts, initiateAchTransfer, initiateUnifiedFundsTransfer), link external bank accounts through Plaid/Finicity, and schedule one-time and recurring transfers.

- **Human URL:** [https://docs.highnote.com/docs/api-reference/mutation](https://docs.highnote.com/docs/api-reference/mutation)
- **Base URL:** `https://api.us.highnote.com/graphql`

#### Tags

- Transfers
- ACH
- Money Movement
- Instant Payments
- GraphQL

#### Properties

- [Documentation](https://docs.highnote.com/docs/developers/api/using-the-api)
- [API Reference](https://docs.highnote.com/docs/api-reference/mutation)
- [GraphQL](graphql/highnote-graphql.md) — [GraphQL](https://spec.graphql.org)
- [OpenAPI](openapi/highnote-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/highnote.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/highnote.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Highnote Collaborative Authorization API

Register and manage a collaborative-authorization endpoint (addCollaborativeAuthorizationEndpoint, activateCollaborativeAuthorizationEndpoint) so your service participates in real-time authorization decisions, returning approve or decline responses on each card authorization within the network timeout window.

- **Human URL:** [https://docs.highnote.com/docs/api-reference/mutation](https://docs.highnote.com/docs/api-reference/mutation)
- **Base URL:** `https://api.us.highnote.com/graphql`

#### Tags

- Collaborative Authorization
- Real-time Decisioning
- Webhooks
- GraphQL

#### Properties

- [Documentation](https://docs.highnote.com/docs/developers/api/using-the-api)
- [API Reference](https://docs.highnote.com/docs/api-reference/mutation)
- [GraphQL](graphql/highnote-graphql.md) — [GraphQL](https://spec.graphql.org)
- [OpenAPI](openapi/highnote-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/highnote.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/highnote.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Highnote Webhooks & Notifications API

Register HTTPS webhook notification targets (addWebhookNotificationTarget), activate and deactivate them, and subscribe to event types (addSubscriptionsToNotificationTarget) so Highnote pushes account, card, transaction, and transfer events to your systems. Events are also queryable via notificationEvents.

- **Human URL:** [https://docs.highnote.com/docs/api-reference/mutation](https://docs.highnote.com/docs/api-reference/mutation)
- **Base URL:** `https://api.us.highnote.com/graphql`

#### Tags

- Webhooks
- Notifications
- Events
- Subscriptions
- GraphQL

#### Properties

- [Documentation](https://docs.highnote.com/docs/developers/api/using-the-api)
- [API Reference](https://docs.highnote.com/docs/api-reference/mutation)
- [GraphQL](graphql/highnote-graphql.md) — [GraphQL](https://spec.graphql.org)
- [OpenAPI](openapi/highnote-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/highnote.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/highnote.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/Highnote-Platform)
- [LinkedIn](https://www.linkedin.com/company/highnote-platform)
- [Website](https://highnote.com)
- [Documentation](https://docs.highnote.com)
- [Plans](plans/highnote-plans-pricing.yml)
- [Rate Limits](rate-limits/highnote-rate-limits.yml)
- [Fin Ops](finops/highnote-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
