# Highnote

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Highnote is a modern, unified embedded-finance and banking-as-a-service platform for card issuing, card acquiring, credit, and real-time money movement, with a built-in real-time programmable ledger and full program management. The entire platform is driven by a single GraphQL API at https://api.us.highnote.com/graphql (test https://api.us.test.highnote.com/graphql), authenticated with a base64-encoded API key over HTTP Basic auth. One endpoint covers card products, US person and business account holders (KYC/KYB onboarding), financial accounts and credit lines, virtual/physical/tokenized payment cards, transaction authorization and clearing, disputes, spend and velocity rules, collaborative authorization, multi-rail money movement (ACH, wire, RTP, push-to-card), and outbound webhook event notifications. Highnote is a US-based platform serving digital-first businesses embedding financial products; access is enterprise, contract-gated, with self-serve dashboard signup and a test environment.

**Areas:** Card Issuing · Card Acquiring · Embedded Finance · Banking as a Service · Fintech · Payments · GraphQL · Ledger · Credit · Money Movement · ACH · KYC

## Highnote on APIs.io

Everything profiled for Highnote is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/highnote/](https://apis.io/providers/highnote/)** — or go straight to one of the APIs or properties below.

### APIs (1)

- [Highnote Graph QL API](https://apis.io/apis/highnote/highnote-graph-ql-api/) — Single GraphQL endpoint for all Highnote operations.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Highnote Event Notifications](https://apis.io/asyncapis/highnote/highnote-events-asyncapi/)

#### Event channels (1)

Individual events and webhooks the provider emits.

- [/](https://apis.io/channels/highnote/notifications/)

#### GraphQL (1)

GraphQL schemas.

- [Highnote GraphQL API](https://apis.io/graphqls/highnote/highnote-graphql/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [highnote](https://apis.io/servers/highnote/highnote/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Highnote Agentic Access](https://apis.io/agentic-access/highnote/highnote-agentic-access/)

#### Collections (3)

Postman and Open Collection request collections.

- [Highnote GraphQL API](https://apis.io/collections/highnote/open-highnote/)
- [Highnote GraphQL API](https://apis.io/collections/highnote/open-highnote-graphql-api/)
- [Highnote GraphQL API](https://apis.io/collections/highnote/postman-highnote-graphql-api/)

#### Overlays (2)

OpenAPI overlays, including conversational phrasing for each operation.

- [Highnote Graph Ql Api Phrasing Overlay](https://apis.io/overlays/highnote/highnote-graph-ql-api-phrasing-overlay/)
- [Highnote Graphql Api Overlay](https://apis.io/overlays/highnote/highnote-graphql-api-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Highnote Authentication](https://apis.io/security/highnote/highnote-authentication/)
- [Highnote Domain Security](https://apis.io/security/highnote/highnote-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Highnote Plans Pricing](https://apis.io/plans/highnote/highnote-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Highnote Rate Limits](https://apis.io/rate-limits/highnote/highnote-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Highnote Finops](https://apis.io/finops/highnote/highnote-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://highnote.com)
- [Documentation](https://docs.highnote.com)
- [Getting started](https://docs.highnote.com/docs/get-started/about-highnote)
- [API reference](https://docs.highnote.com/docs/tags/api)
- [Pricing](https://highnote.com/pricing)
- [Support](https://support.highnote.com/hc/en-us)
- [Blog](https://highnote.com/blog)
- [Compliance](https://docs.highnote.com/docs/get-started/introduction/pci-dss-compliance)
- [Terms of service](https://highnote.com/agreements/terms/01-05-22)
- [Privacy policy](https://highnote.com/agreements/privacy)
- [GitHub](https://github.com/Highnote-Platform)
- [Status](https://status.highnote.com)

## API Evangelist rating

**Kin Score 60.9** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 62.1 |
| Contract governance | 18.2 |
| Operational transparency | 55.3 |
| Developer ergonomics | 74.4 |
| Access clarity | 57.9 |

**Agent readiness 31.0** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 39.3** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/highnote/](https://apis.io/providers/highnote/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Highnote: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/highnote/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
