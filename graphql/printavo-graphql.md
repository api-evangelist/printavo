# Printavo API v2 (GraphQL)

Printavo API v2 is a **native GraphQL API** for print shop management - quotes,
invoices, orders, customers, contacts, line items, imprints, production statuses,
tasks, payments, and Printavo Merch stores. It replaces Printavo's legacy REST
API, which was maintained through 2024; only API v2 receives ongoing updates.

- **Endpoint:** `https://www.printavo.com/api/v2` (single POST GraphQL endpoint)
- **Documentation:** https://www.printavo.com/docs/api/v2
- **Query reference:** https://www.printavo.com/docs/api/v2/operation/query/
- **Mutation reference:** https://www.printavo.com/docs/api/v2/operation/mutation
- **Schema (this repo):** [printavo-schema.graphql](printavo-schema.graphql)
- **Example operations (this repo):** [printavo-queries.graphql](printavo-queries.graphql)

## Access model

API access is **gated to Printavo's Premium subscription tier**. The Lite and
Standard plans do not include API access. The public docs and schema are readable
by anyone, but a live API token is only issued on a Premium account. This is why
the endpoints in this catalog are honestly modeled from the published reference
rather than exercised against a live token.

## Authentication

Every request sends two custom headers plus JSON content type:

```
Content-Type: application/json
email: you@yourshop.com
token: <API token from My Account>
```

The `token` is generated on the **My Account** page of a Premium Printavo
account. There is also a `login` mutation that exchanges email/password for a
token.

## Limits

- **Rate limit:** 10 requests every 5 seconds, per user email or IP address.
- **Query complexity limit:** 25,000.
- **Maximum query depth:** 13 levels.
- **Pagination:** Connections return 25 nodes per page by default and use
  cursor-based args (`first`, `last`, `after`, `before`).

## Core model

- **Order** is a GraphQL union of **Quote** and **Invoice**. Query `order`/`orders`
  to work across both, or `quote`/`quotes` and `invoice`/`invoices` for one kind.
- A quote/invoice contains **Line Item Groups**, which contain **Line Items**
  (garments/products with per-size quantities) and **Imprints** (the decoration).
- **Status** tracks an order through the shop; move an order with `statusUpdate`.
- **Task** and **ApprovalRequest** attach to quotes and invoices for production
  work and artwork/quote approvals.
- **Customer** (company) has **Contacts**, **Orders**, and **Reminders**.
- **Transaction** / **PaymentRequest** cover money movement.
- **MerchStore** / **MerchOrder** cover the Printavo Merch online-store add-on.

## Example

```graphql
query RecentOrders {
  orders(first: 10, sortOn: "createdAt", sortDescending: true) {
    edges {
      node {
        ... on Quote {
          id
          visualId
          nickname
          total
          status { name color type }
          contact { fullName email }
        }
        ... on Invoice {
          id
          visualId
          total
          paidInFull
          status { name }
        }
      }
    }
  }
}
```
