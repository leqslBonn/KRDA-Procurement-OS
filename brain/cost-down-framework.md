---
id: framework-cost-down
title: Cost Down Framework
type: framework
used_by: [../workflows/cost_down.md, ../skills/cost_breakdown.md]
status: active
updated: 2026-06-25
---

# Cost Down Framework

> The logic for choosing which cost-reduction lever to pursue and validating the saving.

## Purpose
Pick the highest-value, lowest-risk lever for a part/category — without compromising spec.

## When to Use
Inside [cost_down.md](../workflows/cost_down.md) (identify-lever step).

## Decision Inputs

| Input | Source |
|-------|--------|
| Should-cost & baseline | [cost_breakdown](../skills/cost_breakdown.md) |
| Gap vs price/quotes | `/rfq`, `/cost_down` |
| Spec constraints | Technical Purchasing |

## Framework (levers & when to use)

| Lever | Use when | Risk |
|-------|----------|------|
| Negotiation | Price > should-cost, supplier has room | low |
| VA / VE | Design/process inefficiency exists | spec change |
| Re-sourcing | Current supplier uncompetitive, alt qualified | switching |
| Volume / consolidation | Fragmented spend, scale available | dependency |
| Payment / terms | Cash/terms value available | low |
| Localization | Import cost / FX / logistics high | qualification |

## Decision Rule
- Rank levers by **(expected saving × probability) ÷ risk & effort**.
- Spec-changing levers (VA/VE, localization) route through
  [engineering-change-framework](engineering-change-framework.md).
- A saving counts only when **validated vs a sourced baseline**.

## Escalation / Commitment Gate
- Realizing a saving (price change) = **D3 → Human Owner**. Spec change = **D3**.

## Pitfalls
- ❌ Claiming unvalidated savings.
- ❌ Hidden quality loss to hit a target.
- ❌ Ignoring switching/qualification cost in re-sourcing.

## Links
- Workflow: [cost_down.md](../workflows/cost_down.md) · Skill: [cost_breakdown.md](../skills/cost_breakdown.md)
- Frameworks: [negotiation-framework](negotiation-framework.md), [make-vs-buy](make-vs-buy.md)
- Knowledge: `../knowledge/cost-engineering/`
