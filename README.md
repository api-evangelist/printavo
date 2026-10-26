# Printavo (printavo)

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

Printavo is print shop management software for screen printers, embroiderers, and
other decorated-apparel businesses, covering quotes, invoices, orders, customers,
contacts, line items, imprints, production statuses, tasks, payments, and Printavo
Merch online stores.

Printavo exposes a **native GraphQL API (API v2)** at `https://www.printavo.com/api/v2`,
which replaces its legacy REST API (maintained through 2024; only v2 receives
ongoing updates). Requests authenticate with two custom headers - `email` and
`token` (the token is generated on the My Account page) - plus
`Content-Type: application/json`.

**Access model (be honest):** API access is **gated to Printavo's Premium
subscription tier**. The Lite ($109/mo) and Standard ($244/mo) plans do not
include API access; only Premium (quote-based) does. The developer docs and
GraphQL schema are publicly readable, but a live token requires a paid Premium
account. Because the API could not be exercised against a live Premium token, the
operations captured here are **honestly modeled from Printavo's published
query/mutation/object reference** - operation names, auth, and limits are grounded
in the public docs; some mutation input shapes are modeled. See `review.yml` for
the full grounding notes (`endpointsModeled: true`).

**Documented limits:** 10 requests / 5 seconds (per email or IP), query
complexity limit 25,000, maximum query depth 13, connections default to 25 nodes
per page (cursor pagination).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/printavo/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/printavo/refs/heads/main/apis.yml)

## Tags

- Print Shop Management
- Screen Printing
- Embroidery
- Quotes
- Invoices
- Orders
- GraphQL
- Decorated Apparel

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

Printavo API v2 is a single GraphQL endpoint; the entries below are logical
groupings of that one endpoint's operations. All share the base URL
`https://www.printavo.com/api/v2` and are documented at
[https://www.printavo.com/docs/api/v2](https://www.printavo.com/docs/api/v2).

### Printavo Quotes API

Query a single quote or a paginated quotes connection, and create, update,
delete, or duplicate quotes (`quoteCreate`, `quoteUpdate`, `quoteDelete`,
`quoteDuplicate`). Covers financials, production/payment due dates, status,
contact, and line item groups.

### Printavo Invoices API

Query a single invoice or an invoices connection, and update, delete, or
duplicate invoices (`invoiceUpdate`, `invoiceDelete`, `invoiceDuplicate`). An
invoice is a quote converted into a billable order.

### Printavo Orders API

Query `order` / `orders`, where an order is the GraphQL union of quotes and
invoices, with filtering by production dates and statuses. Orders are modified
through their underlying quote, invoice, and line item mutations.

### Printavo Customers and Contacts API

Query single or plural customers and contacts, and create/update/delete them
(`customerCreate`, `contactCreate`, etc.). Customers expose `contacts`, `orders`,
and `reminders` connections.

### Printavo Line Items API

Query line items and line item groups, and create/update/delete line items, line
item groups, imprints, and fees - including batch variants (`lineItemCreates`,
`lineItemUpdates`).

### Printavo Statuses API

Query `status` / `statuses` and move an order between production stages with
`statusUpdate`. Each status has a name, color, type, and position.

### Printavo Tasks API

Query single or plural tasks with sorting, and create/update/delete tasks
(`taskCreate`, `taskUpdate`, `taskDelete`), plus manage artwork/quote approvals
via the `approvalRequest` mutations.

### Printavo Payments API

Query transactions, transaction details, and payment requests, and record,
update, or delete payments (`transactionPaymentCreate`, etc.).

### Printavo Merch API

Query merch orders and merch stores (a separately priced $109/mo add-on) to pull
online group-store sales into the same order and production workflow.

## GraphQL

- [GraphQL Overview](graphql/printavo-graphql.md)
- [GraphQL Schema (partial, grounded)](graphql/printavo-schema.graphql)
- [Example Operations](graphql/printavo-queries.graphql)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/printavo)
- [Website](https://www.printavo.com/)
- [Documentation](https://www.printavo.com/docs/api/v2)
- [Plans](plans/printavo-plans-pricing.yml)
- [Rate Limits](rate-limits/printavo-rate-limits.yml)
- [Fin Ops](finops/printavo-finops.yml)
- [Blog](https://www.printavo.com/blog/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
