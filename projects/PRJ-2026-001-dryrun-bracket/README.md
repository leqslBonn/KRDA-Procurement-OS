---
id: PRJ-2026-001
title: DRY-RUN — Machined Bracket Sourcing (pipeline readiness test)
owner: Chief of Staff
status: active
updated: 2026-06-26
links: [../../workflows/ENGINE.md, ../../brain/rfq-evaluation-framework.md, ../../knowledge/cost-engineering/should-cost-method.md]
---

# DRY-RUN — Machined Bracket Sourcing  (PRJ-2026-001)

> **SYNTHETIC pipeline test** (not a real KRDA buy). Purpose: run one case through the
> full [Workflow Engine](../../workflows/ENGINE.md) before go-live, prove it works,
> and surface gaps. All numbers `EST`/synthetic.

## Pipeline Trace (engine stages)

| # | Stage | Result |
|---|-------|--------|
| 1 | Request | Source new bracket, EAU 50,000/yr |
| 2 | Classify | Sourcing + award → **D3** (annual value > 2M THB) |
| 3 | Breakdown | spec check · should-cost · shortlist · quote · evaluate |
| 4 | Assign | SE (spec/sourcing), CC (cost/RFQ), SM (risk), TS (PR/PO) |
| 5 | Technical Review | SS400 plate, 0.4 kg, laser+bend+tap+powder coat — buildable; spec controlled |
| 6 | Business Review | 3 qualified suppliers available; multi-source viable |
| 7 | Risk Review | No single-source risk; commodity part — low |
| 8 | Cost Review | Should-cost below |
| 9 | Conflicts | none |
| 10 | CoS Review | balanced, evidence-based |
| 11 | Executive Recommendation | below → Human Owner |
| 12 | Archive | this record + lesson |

## Should-Cost (KB-CE rates, all `EST`)

| Element | Basis | Calc | THB/pc |
|---------|-------|------|-------:|
| Material | SS400 plate 30 THB/kg | 0.4 kg × 1.15 (scrap) × 30 | 13.8 |
| Laser cut | 1,200 THB/hr | 0.008 hr | 9.6 |
| Press brake | 900 THB/hr | 0.006 hr | 5.4 |
| Tapping | 450 THB/hr | 0.004 hr | 1.8 |
| Powder coat | 250 THB/m² | 0.04 m² | 10.0 |
| **Conversion subtotal** | | | 26.8 |
| **Manufacturing cost** | material + conversion | | **40.6** |
| Overhead + SG&A + profit | +20% (KB-CE-005) | × 1.20 | 8.1 |
| **Should-cost / pc** | | | **≈ 48.7** |

> Annual should-cost spend ≈ 50,000 × 48.7 ≈ **2.44M THB/yr**.

## Quotes (synthetic) & Evaluation ([rfq-evaluation-framework](../../brain/rfq-evaluation-framework.md))

| Supplier | Unit price | Tech | Quality | Lead | Risk | Weighted |
|----------|-----------:|------|---------|------|------|---------:|
| A (qualified) | 47 | pass | strong | 3 wk | low | **best** |
| B (qualified) | 45 | pass | adequate | 4 wk | med | 2nd |
| C (conditional) | 43 | pass | weak | 5 wk | high | excluded (qual gate) |

Best total value: **Supplier A @ 47 THB** (−3.5% vs should-cost; quality/lead justify the gap vs B).

## Executive Recommendation

- **Recommendation:** award bracket to **Supplier A @ 47 THB/pc** (3-week lead, strong quality).
- **Evidence:** should-cost 48.7 THB (KB-CE rates); A is below should-cost with best
  quality/lead; C excluded on qualification gate.
- **Decision required (Human Owner):** annual value ≈ 2.44M THB → per
  [approval-matrix](../../brain/approval-matrix.md): **> 2M → President** + **competitive
  bidding required (> 1M)**. Award is **D3** — President approval after bidding.

## ✅ Gaps Found (readiness value)

1. **Bidding trigger:** annual value > 1M → must run **competitive bidding**, not a
   simple price comparison. Confirm whether KRDA bids on *annual* value or *per-PO*. → clarify in procedure.
2. **Rates are `EST`** — should-cost swings with real material/process quotes. Calibrate
   KB-CE rates from 2–3 real quotes before live use.
3. **No real supplier records** — A/B/C are synthetic; need real qualified suppliers in `/suppliers`.
4. **Per-PO vs annual approval band** ambiguity in approval-matrix — needs a rule for
   blanket/annual agreements vs single PO.
5. Pipeline itself (engine stages, frameworks, gate routing) **worked end-to-end** ✅.

## Lesson (→ lessons_learned)
Pipeline is sound; the binding gaps before go-live are **real rates + real suppliers +
annual-vs-PO approval rule**, not the system structure.
