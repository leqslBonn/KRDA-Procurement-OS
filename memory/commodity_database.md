---
id: commodity-database
title: Commodity Database (Recall Index)
type: register-index
status: active
updated: 2026-06-25
---

# Commodity Database (Recall Index)

> Index of the commodities/materials KRDA buys, mapping each to its knowledge,
> suppliers, and cost basis. **Index only — not the source of truth.**

## Source of Truth
Commodity definitions, standards, and cost rates are canonical in
[`/knowledge`](../knowledge/README.md) (`taxonomy/`, `standards/`, `cost/`).
Suppliers are canonical in [`/suppliers`](../suppliers/README.md). This file maps
commodity ↔ knowledge ↔ suppliers for fast recall — it copies neither.

## Schema

| Commodity ID | Name | Category | Spec/Standard | Cost-rate ref | Suppliers | Notes |
|--------------|------|----------|---------------|---------------|-----------|-------|
| _CMD-example_ | _Steel casting_ | _raw/process_ | _`../knowledge/standards/...`_ | _`../knowledge/cost/...`_ | _supplier links_ | _TBD_ |

> No commodities catalogued yet. Populate from `/knowledge/taxonomy/spend-categories.md` when authored.

## Conventions
- One row per commodity/material family.
- `Spec/Standard` and `Cost-rate ref` link to `/knowledge`; `Suppliers` link to `/suppliers`.
- Align IDs/names with the spend taxonomy in `/knowledge/taxonomy`.

## Links
- Knowledge: [`/knowledge`](../knowledge/index.md) (taxonomy, standards, cost)
- Suppliers: [supplier_database.md](supplier_database.md)
- Cost basis: [cost_database.md](cost_database.md)
