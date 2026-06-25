---
id: negotiation-history
title: Negotiation History (Register)
type: register-native
status: active
updated: 2026-06-25
---

# Negotiation History (Register)

> Record of every negotiation: target, outcome, levers that worked, and the
> supplier's behavior. **Memory-native: the source of truth for negotiation
> outcomes**, feeding future [negotiation-framework](../brain/negotiation-framework.md) prep.

## Why
Negotiation knowledge compounds — what worked with a supplier last time informs the
next round. The Memory Engine appends here when a negotiation closes.

## Schema (newest on top)

| Date | Supplier | Part/Scope | Ref | Target | Outcome | Δ vs target | Levers used | Notes |
|------|----------|-----------|-----|--------|---------|-------------|-------------|-------|
| _2026-06-25_ | _example_ | _..._ | _RFQ-/CD-_ | _..._ | _..._ | _..._ | _volume/term_ | _..._ |

> No negotiations logged yet.

## Conventions
- One row per closed negotiation; `Ref` links the RFQ/cost record.
- Capture **levers that worked** and supplier behavior for reuse.
- Confidential: no competing-supplier prices here.
- Append-only; never delete.

## Links
- Framework: [negotiation-framework](../brain/negotiation-framework.md)
- Workflow: [price_negotiation](../workflows/price_negotiation.md)
- Knowledge: [knowledge/negotiation](../knowledge/negotiation/README.md)
