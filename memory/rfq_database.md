---
id: rfq-database
title: RFQ Database (Recall Index)
type: register-index
status: active
updated: 2026-06-25
---

# RFQ Database (Recall Index)

> Index of all RFQs and their outcomes. **Index only — not the source of truth.**

## Source of Truth
Canonical RFQ records (packages, quotes, bid tabs, awards) live in
[`/rfq`](../rfq/README.md). Quotes are **confidential** and stay in the record —
never copied into this index.

## Schema (newest on top)

| RFQ ID | Part/Scope | Status | Issued | Due | #Quotes | Awarded | Award vs Target | Record |
|--------|-----------|--------|--------|-----|---------|---------|-----------------|--------|
| _RFQ-2026-001_ | _example_ | _draft_ | _—_ | _—_ | _0_ | _—_ | _TBD_ | _`../rfq/RFQ-2026-001-.../`_ |

> No RFQs yet.

## Conventions
- One row per RFQ; `Record` links to `../rfq/<id>/`.
- `Status`: draft → issued → quoting → evaluating → awarded → archived.
- **Never** put supplier prices/identities-vs-price in this index (confidentiality).
- `Award vs Target` summarizes variance only after Human Owner approval.

## Links
- Canonical records: [`/rfq`](../rfq/README.md)
- Workflow: [`rfq.md`](../workflows/rfq.md)
- Cost targets: [cost_database.md](cost_database.md)
