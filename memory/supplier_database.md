---
id: supplier-database
title: Supplier Database (Recall Index)
type: register-index
status: active
updated: 2026-06-25
---

# Supplier Database (Recall Index)

> Fast-lookup index of all suppliers. **Index only — not the source of truth.**

## Source of Truth
Canonical supplier records live in [`/suppliers`](../suppliers/README.md). This
file is a recall index: it holds lightweight pointers and status, and **links**
to each record. Never copy supplier facts here — update the record, then the
index row.

## Schema

| Supplier ID | Name | Commodity/Category | Country | Qual. status | Scorecard | Record |
|-------------|------|--------------------|---------|--------------|-----------|--------|
| _SUP-example_ | _Example Co._ | _casting_ | _TH_ | _qualified_ | _link_ | _`../suppliers/example-co/`_ |

> No real suppliers onboarded yet. Add a row when a record is created in `/suppliers`.

## Conventions
- One row per supplier; `Record` links to `../suppliers/<slug>/`.
- `Qual. status` mirrors the canonical status in the supplier record.
- Sort by Commodity/Category, then Name.

## Links
- Canonical records: [`/suppliers`](../suppliers/README.md)
- By commodity: [commodity_database.md](commodity_database.md)
- Supplier risks: [risk_database.md](risk_database.md)
