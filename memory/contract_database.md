---
id: contract-database
title: Contract Database (Recall Index)
type: register-index
status: active
updated: 2026-06-25
---

# Contract Database (Recall Index)

> Index of all contracts and agreements (incl. NDAs) and their expiries. **Index
> only — not the source of truth.**

## Source of Truth
Canonical contracts and key terms live in [`/contracts`](../contracts/README.md).
Terms are **confidential** and stay in the record — this index holds only
identity, type, status, and dates, and links to the record.

## Schema (newest on top)

| Contract ID | Supplier | Type | Status | Effective | Expiry | Key-terms record |
|-------------|----------|------|--------|-----------|--------|------------------|
| _CTR-2026-001_ | _example_ | _NDA_ | _draft_ | _—_ | _—_ | _`../contracts/CTR-2026-001-.../`_ |

> No contracts yet.

## Conventions
- One row per contract; `Type`: NDA / supply / pricing / framework.
- `Status`: draft → under-review → approved → active → expired/archived.
- **Every `Expiry` is mirrored to** [`/schedule`](../schedule/README.md) for renewal review.
- Confidential terms never appear here — link the record.

## Links
- Canonical records: [`/contracts`](../contracts/README.md)
- NDA workflow: [`nda.md`](../workflows/nda.md)
- Renewal calendar: [`/schedule`](../schedule/README.md)
