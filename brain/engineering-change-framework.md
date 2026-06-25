---
id: framework-engineering-change
title: Engineering Change Framework
type: framework
used_by: [../workflows/engineering_change.md]
status: active
updated: 2026-06-25
---

# Engineering Change Framework

> The logic for assessing an ECN's purchasing impact and deciding cut-in.

## Purpose
Make engineering changes buyable and safe — assess every impact, then cut in cleanly.

## When to Use
Inside [engineering_change.md](../workflows/engineering_change.md).

## Decision Inputs

| Input | Source |
|-------|--------|
| ECN (old→new, reason) | Engineering / `/projects` |
| Affected part & supplier | `/suppliers`, `/projects` |
| Standards | `../knowledge/engineering-standards/` |

## Framework (impact dimensions — none skipped)

| Dimension | Question | Owner |
|-----------|----------|-------|
| Technical | New spec/qual needed? | Tech Purchasing |
| Supplier | Can supplier meet it? re-qual? | Supplier Dev |
| Cost | Price/tooling/obsolescence delta? | Cost Reduction |
| Sourcing | Make/buy or source-list change? | Strat Sourcing |
| Transaction | Master data / open-PO impact? | SAP Purchasing |
| Timing | Cut-in point, old-stock run-out | Tech Purchasing |

## Decision Rule
- Consolidate all six impacts before deciding (no partial assessment).
- Cut-in only after: spec controlled, re-qual (if needed) done, price agreed,
  obsolescence quantified.
- Sequence: re-qual → price → master data → cut-in.

## Escalation / Commitment Gate
- Change execution / cut-in = **D3 → Human Owner**. Controlled-spec change = **D3**.

## Pitfalls
- ❌ Cutting in before re-qualification.
- ❌ Skipping a department's impact.
- ❌ Ignoring old-stock obsolescence cost.

## Links
- Workflow: [engineering_change.md](../workflows/engineering_change.md)
- Frameworks: [technical-purchasing-framework](technical-purchasing-framework.md), [cost-down-framework](cost-down-framework.md)
- Knowledge: `../knowledge/mechanical/`, `../knowledge/engineering-standards/`
