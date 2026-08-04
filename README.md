# Highnote (highnote)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
