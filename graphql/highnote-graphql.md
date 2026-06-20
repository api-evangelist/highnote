# Highnote GraphQL API

The [Highnote](https://highnote.com/) embedded-finance platform exposes a **single GraphQL
endpoint** that drives the entire product: card issuing, account holders, financial accounts,
transactions, transfers, collaborative authorization, spend/velocity rules, and webhook
notifications.

- API docs: <https://docs.highnote.com/docs/developers/api/using-the-api>
- Intro to GraphQL: <https://docs.highnote.com/docs/developers/api/intro-to-graphql>
- API reference (Query / Mutation / Object / Input): <https://docs.highnote.com/docs/api-reference/query>
- API Explorer: <https://docs.highnote.com/explorer>
- GitHub: <https://github.com/Highnote-Platform>

---

## Endpoint

| Environment | URL |
|-------------|-----|
| Live | `https://api.us.highnote.com/graphql` |
| Test | `https://api.us.test.highnote.com/graphql` |

All operations — queries and mutations — are sent as `POST` requests with a
`Content-Type: application/json` body containing a `query` (or `mutation`) string and an
optional `variables` object. There is no REST surface; the GraphQL endpoint is the API.

---

## Authentication

Highnote uses **HTTP Basic authentication** with a **base64-encoded API key** set as the
username (no password):

```bash
# Generate an API key in the Highnote Dashboard, then base64-encode it:
echo -n 'YOUR_ASCII_API_KEY' | base64

# Pass it on every request:
Authorization: Basic YOUR_BASE64_ENCODED_API_KEY
```

```bash
curl https://api.us.highnote.com/graphql \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Authorization: Basic YOUR_BASE64_ENCODED_API_KEY" \
  -d '{"query":"query { ping }"}'
```

The API also supports **idempotency keys**, **HQL** (Highnote Query Language) search, custom
metadata / user-defined fields, **Relay cursor connection** pagination (`first` / `after`), and
per-account rate limiting.

---

## Schema file

See [`highnote-schema.graphql`](./highnote-schema.graphql) for a representative SDL of the
main types, queries, and mutations. It is a **representative subset** distilled from the public
documentation, not the full machine-generated schema (which is large and uses many union and
input types).

---

## Domains

| Domain | Description | Representative operations |
|--------|-------------|---------------------------|
| Card Products | Define a card program | `createCardProduct`, `enableCreditCardFeature`, `enableCollaborativeAuthorizationFeature` |
| Account Holders | Onboard persons & businesses (KYC/KYB) | `createUSPersonAccountHolder`, `createUSBusinessAccountHolder`, `createAccountHolderCardProductApplication` |
| Financial Accounts | Hold funds / credit balances | `issueFinancialAccountForApplication`, `assignPaymentCardToFinancialAccount` |
| Payment Cards | Issue virtual / physical / digital cards | `issuePaymentCardForApplication`, `activatePaymentCard`, `closePaymentCard`, `createPhysicalCardGroupOrder` |
| Transactions | Authorize, capture, charge, dispute | `authorizePaymentCard`, `capturePaymentTransaction`, `chargePaymentCard`, `initiateCustomerCardTransactionDispute` |
| Transfers | Move money (ACH, wire, instant) | `initiateTransferBetweenFinancialAccounts`, `initiateAchTransfer`, `initiateUnifiedFundsTransfer` |
| Collaborative Authorization | Real-time decisioning hook | `addCollaborativeAuthorizationEndpoint`, `activateCollaborativeAuthorizationEndpoint` |
| Spend & Velocity Rules | Program controls | `createAmountLimitSpendRule`, `createMerchantCategorySpendRule`, `createVelocityRule` |
| Webhooks / Notifications | Event delivery | `addWebhookNotificationTarget`, `addSubscriptionsToNotificationTarget`, `activateNotificationTarget` |

---

## Query examples

### Health check

```graphql
query {
  ping
}
```

### Look up a node by global ID

```graphql
query GetNode($id: ID!) {
  node(id: $id) {
    id
    __typename
  }
}
```

### List card products

```graphql
query {
  cardProducts(first: 10) {
    edges {
      node {
        id
        name
        type
        status
      }
    }
    pageInfo {
      hasNextPage
      endCursor
    }
  }
}
```

### Fetch a financial account with balances

```graphql
query GetFinancialAccount($id: ID!) {
  node(id: $id) {
    ... on FinancialAccount {
      id
      name
      status
      balances {
        availableBalance { value currencyCode }
        ledgerBalance { value currencyCode }
      }
    }
  }
}
```

### Search payment transactions

```graphql
query {
  paymentTransactions(first: 25) {
    edges {
      node {
        id
        status
        approvedAmount { value currencyCode }
        merchantDetails { name category }
      }
    }
  }
}
```

---

## Mutation examples

### Create a US person account holder

```graphql
mutation CreatePerson($input: CreateUSPersonAccountHolderInput!) {
  createUSPersonAccountHolder(input: $input) {
    id
    name { givenName familyName }
    status
  }
}
```

### Issue a financial account for an approved application

```graphql
mutation IssueFinancialAccount($applicationId: ID!) {
  issueFinancialAccountForApplication(input: { applicationId: $applicationId }) {
    id
    status
  }
}
```

### Issue and assign a virtual payment card

```graphql
mutation IssueCard($applicationId: ID!) {
  issuePaymentCardForApplication(input: { applicationId: $applicationId, formFactor: VIRTUAL }) {
    id
    bin
    last4
    expirationDate
    network
    status
  }
}
```

### Authorize a card transaction (acquiring)

```graphql
mutation Authorize($input: AuthorizePaymentCardInput!) {
  authorizePaymentCard(input: $input) {
    id
    status
    approvedAmount { value currencyCode }
  }
}
```

### Initiate a transfer between financial accounts

```graphql
mutation Transfer($input: InitiateTransferInput!) {
  initiateTransferBetweenFinancialAccounts(input: $input) {
    id
    status
    amount { value currencyCode }
  }
}
```

### Register a webhook notification target

```graphql
mutation AddWebhook($input: AddWebhookNotificationTargetInput!) {
  addWebhookNotificationTarget(input: $input) {
    id
    url
    status
  }
}
```

### Add a collaborative authorization endpoint

```graphql
mutation AddCollabAuth($input: AddCollaborativeAuthorizationEndpointInput!) {
  addCollaborativeAuthorizationEndpoint(input: $input) {
    id
    url
    status
  }
}
```

> Note: Highnote does **not** publish a public GraphQL **subscription** surface. Realtime/event
> delivery is handled out-of-band via **webhook notification targets** (push over HTTPS) and, for
> authorization decisioning, the **collaborative authorization endpoint** that Highnote calls
> synchronously during each authorization.
