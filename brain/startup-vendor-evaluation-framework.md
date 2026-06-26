---
id: framework-startup-vendor-evaluation
title: Startup / Software Vendor Evaluation Framework
type: framework
used_by: [../templates/vendor-pitch-scorecard.md, ../knowledge/procurement/saas-tco.md, ../knowledge/procurement/poc-evaluation.md]
status: active
updated: 2026-06-26
---

# Startup / Software Vendor Evaluation Framework

> The criteria and logic for evaluating **IoT / smart-farm / software startup vendors**
> — where the risk is not "wrong tolerance" but "wrong partner who may fold, lock you
> in, or own your data."

## Purpose
Pick the right technology vendor on **total value + continuity + data control**, not the
slickest pitch or lowest sticker price. Built for sitting in pitch sessions and choosing.

## When to Use
Evaluating IoT/smart-farm/app vendors — pitch sessions, RFPs, POC decisions. Pairs with
the [vendor pitch scorecard](../templates/vendor-pitch-scorecard.md). Reuses
[decision-matrix](decision-matrix.md) for the scoring math.

## Decision Inputs

| Input | Source |
|-------|--------|
| Vendor pitch / proposal / demo | the pitch session |
| TCO (3–5 yr) | [saas-tco](../knowledge/procurement/saas-tco.md) |
| POC result (if any) | [poc-evaluation](../knowledge/procurement/poc-evaluation.md) |
| References / traction | customer checks |

## Framework (criteria & weights)

| # | Criterion | Weight | Score 1–5 = ? |
|---|-----------|:---:|----------------|
| 1 | Problem–solution fit | 15% | Solves a real KRDA/smart-farm need, clear use case |
| 2 | Technology & product maturity | 15% | Working product/demo vs slideware (TRL) |
| 3 | Team & domain capability | 10% | Technical depth + understands agriculture |
| 4 | Traction & references | 10% | Paying customers, pilots, verifiable references |
| 5 | Scalability | 10% | Scales to KRDA deployment size/sites |
| 6 | Integration & interoperability | 10% | APIs, fits existing systems/data |
| 7 | **Data ownership & security** | 10% | **GATE** — KRDA owns farm data; security adequate |
| 8 | TCO (3–5 yr) | 10% | Total cost incl. subscription/cloud/integration/support |
| 9 | **Startup viability & continuity** | 5% | **GATE** — funding runway; survives; escrow/exit plan |
| 10 | Lock-in / portability | 3% | Open vs proprietary; data export; switching cost |
| 11 | Support & SLA | 2% | Response, maintenance, updates |

Weights are the default; adjust per use case and **record the change**.

## Gates (fail = exclude or POC-only, regardless of score)

- **Data/IP gate:** if KRDA does **not** own its farm/operational data, or security is
  inadequate → exclude (or require contract fix first).
- **Viability gate:** if the startup has no runway / single-person dependency and offers
  **no source-code escrow or continuity plan** → POC-only / conditional, not production.
- **Slideware gate:** no working product for a production decision → POC first, don't buy.

## Decision Rule

1. Apply gates first (data/IP, viability, slideware).
2. Score eligible vendors with the [decision-matrix](decision-matrix.md) (weights above).
3. Compare on **weighted score + TCO** — not pitch polish or upfront price.
4. Recommend: **shortlist → POC** for promising-but-unproven; **award** only after POC +
   contract terms (data ownership, escrow, exit) are secured.

## Escalation / Commitment Gate

- Vendor selection is **D2** (recommendation). Award / contract / subscription commitment =
  **D3 → Human Owner** ([approval-matrix](approval-matrix.md)); data/IP & escrow terms must
  be in the contract before signing.

## Pitfalls

- ❌ Buying on a great demo before checking the product is real (slideware).
- ❌ Ignoring who owns the **data** — the #1 software-vendor trap.
- ❌ No plan for if the **startup folds** (no escrow/continuity).
- ❌ Comparing sticker price instead of 3–5 yr TCO.
- ❌ Letting vendor lock-in slip in (no data export / open standards).

## Links
- Scorecard: [vendor-pitch-scorecard.md](../templates/vendor-pitch-scorecard.md)
- Knowledge: [saas-tco.md](../knowledge/procurement/saas-tco.md), [poc-evaluation.md](../knowledge/procurement/poc-evaluation.md)
- Reuses: [decision-matrix.md](decision-matrix.md), [supplier-risk-framework.md](supplier-risk-framework.md)
- Workflows: [supplier_selection.md](../workflows/supplier_selection.md), [nda.md](../workflows/nda.md)
