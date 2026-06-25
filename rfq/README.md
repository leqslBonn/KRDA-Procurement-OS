# /rfq

The RFQ working area — every quote request and its comparison, filed and
traceable. Owned by the **RFQ Management** agent.

> พื้นที่งาน RFQ — คำขอราคาและตารางเปรียบเทียบ เก็บแบบตรวจสอบย้อนได้

## Structure

```
/rfq
  RFQ-YYYY-NNN-<slug>/
    rfq.md          ← from templates/rfq.md
    quotes/         ← received quotes (confidential)
    bid-tab.md      ← from templates/bid-tab.md
    award.md        ← recommendation + approval record
```

## Conventions

- RFQ ID: `RFQ-YYYY-NNN`. One folder per RFQ.
- Quotes are **confidential** — never expose one supplier's quote to another.
- Compare only on a normalized, like-for-like basis (see bid-tab template).
- Award requires human approval before any commitment; record it in `award.md`.
- Link the originating project (`/projects`) and supplier records (`/suppliers`).

## Lifecycle
`draft → issued → quoting → evaluating → awarded → archived`
