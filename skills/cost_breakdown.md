---
id: skill-cost-breakdown
title: Cost Breakdown (Should-Cost)
type: skill
owner: Cost Reduction (CC)
used_by: [cost_down.md, price_negotiation.md, engineering_change.md]
uses: [../templates/should-cost.md, ../knowledge/cost/]
status: active
updated: 2026-06-25
---

# Cost Breakdown (Should-Cost)

> Build a bottom-up model of a part's fair cost from material, process, labor,
> tooling, overhead, and margin.

## Purpose
Quantify what a part *should* cost so price gaps and negotiation targets are
evidence-based, not guesses.

## When to Use
Inside [cost_down.md](../workflows/cost_down.md) (should-cost step),
[price_negotiation.md](../workflows/price_negotiation.md) (target), and
[engineering_change.md](../workflows/engineering_change.md) (cost impact).

## Inputs

| Input | Source |
|-------|--------|
| Part spec, material, process, EAU | `/projects`, `../company/` |
| Material & process rates | `../knowledge/cost/` *(TBD)* |
| Current price / quotes | `/rfq`, `/cost_down` |

## Method

1. **Define the process** — machining / casting / stamping / molding / assembly.
2. **Material cost** — net mass × rate + scrap/yield.
3. **Process cost** — cycle time × machine rate; setup amortized over batch.
4. **Labor** — touch time × labor rate.
5. **Tooling** — NRE amortized per piece over EAU.
6. **Overhead + SG&A + profit** — apply rates from `../knowledge/cost`.
7. **Sum → should-cost/pc**; compare to current price / best quote / target.

## Output

| Output | Destination / Template |
|--------|------------------------|
| Should-cost model | `../templates/should-cost.md` → `/cost_down/<id>/should-cost.md` |

## Quality Bar
- [ ] Every rate cited with source/date; estimates marked `EST`.
- [ ] Yield/scrap and tooling amortization included.
- [ ] Gap vs current price quantified.

## Common Errors
- ❌ Uncited / assumed rates.
- ❌ Omitting tooling amortization or scrap.
- ❌ Modeling the wrong process for the part.

## Limitations / Guardrails
- A model, not a quote; informs negotiation, does not set price.
- Spec is fixed — cost-down via spec change routes to engineering_change.

## Links
- Workflows: [cost_down.md](../workflows/cost_down.md), [price_negotiation.md](../workflows/price_negotiation.md)
- Template: [should-cost.md](../templates/should-cost.md)
- Knowledge: `../knowledge/cost/`
