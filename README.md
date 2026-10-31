# Printavo

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

Printavo is print shop management software for screen printers, embroiderers, and other decorated-apparel businesses, covering quotes, invoices, orders, customers, line items, production statuses, tasks, payments, and merch stores. Printavo exposes a public GraphQL API (API v2) at www.printavo.com/api/v2 that supersedes its legacy REST API. The GraphQL API is authenticated with an account email plus an API token and is gated to Printavo's Premium subscription tier; the API reference and GraphQL schema are publicly documented at www.printavo.com/docs/api/v2.

**Areas:** Print Shop Management · Screen Printing · Embroidery · Quotes · Invoices · Order · GraphQL · Decorated Apparel

## Printavo on APIs.io

Everything profiled for Printavo is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/printavo/](https://apis.io/providers/printavo/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [Printavo Quotes API](https://apis.io/apis/printavo/printavo-quotes-api/) — GraphQL surface for quotes - the pre-invoice document in Printavo. Query a single quote or a paginated quotes connection, and create, update, delete, or…
- [Printavo Invoices API](https://apis.io/apis/printavo/printavo-invoices-api/) — GraphQL surface for invoices - a quote that has been converted into a billable order. Query a single invoice or an invoices connection, and update, delete,…
- [Printavo Orders API](https://apis.io/apis/printavo/printavo-orders-api/) — GraphQL surface for orders, where an order is the union of quotes and invoices. Query a single order or a paginated orders connection with filtering by…
- [Printavo Customers and Contacts API](https://apis.io/apis/printavo/printavo-customers-api/) — GraphQL surface for customers (companies) and their contacts. Query single or plural customers and contacts, and create, update, or delete them via the…
- [Printavo Line Items API](https://apis.io/apis/printavo/printavo-line-items-api/) — GraphQL surface for the products, garments, and decoration that make up an order. Query line items and line item groups, and create, update, or delete line…
- [Printavo Statuses API](https://apis.io/apis/printavo/printavo-statuses-api/) — GraphQL surface for the production statuses that track an order through the shop. Query a single status or a statuses connection, and move an order between…
- [Printavo Tasks API](https://apis.io/apis/printavo/printavo-tasks-api/) — GraphQL surface for tasks and approval requests attached to quotes, invoices, and orders. Query single or plural tasks with sorting, and create, update, or…
- [Printavo Payments API](https://apis.io/apis/printavo/printavo-payments-api/) — GraphQL surface for payments and money movement. Query transactions, transaction details, and payment requests, and record, update, or delete payments via…
- [Printavo Merch API](https://apis.io/apis/printavo/printavo-merch-api/) — GraphQL surface for Printavo Merch online stores. Query merch orders and merch stores (a separately priced add-on) to pull group-store sales into the same…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### GraphQL (1)

GraphQL schemas.

- [Printavo API v2 (GraphQL)](https://apis.io/graphqls/printavo/printavo-graphql/)

#### Security (1)

Authentication, trust centre, and vulnerability disclosure.

- [Printavo Domain Security](https://apis.io/security/printavo/printavo-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Printavo Plans Pricing](https://apis.io/plans/printavo/printavo-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Printavo Rate Limits](https://apis.io/rate-limits/printavo/printavo-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Printavo Finops](https://apis.io/finops/printavo/printavo-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.printavo.com/)
- [Documentation](https://www.printavo.com/docs/api/v2)
- [Blog](https://www.printavo.com/blog/)

## API Evangelist rating

**Kin Score 12.2** — emerging · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 0.0 |
| Contract governance | 0.0 |
| Operational transparency | 7.9 |
| Developer ergonomics | 19.0 |
| Access clarity | 7.9 |

**Agent readiness 0.6** — human-only

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | — |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 5.9** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/printavo/](https://apis.io/providers/printavo/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Printavo: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/printavo/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
