# Printavo (printavo)

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
