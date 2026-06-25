---
id: wf-cost-down
title: Cost-Down (Should-Cost to Realized Saving)
type: workflow
owner: Cost Reduction (CC)
status: active
updated: 2026-06-25
---

# Cost-Down (Should-Cost to Realized Saving)

> Find, prove, approve, and realize a saving without compromising the spec.

## Flow (BPMN-like)

Legend (canonical: [README](README.md#bpmn-notation)):
`●` start · `[task — Role]` · `◇Gn` gateway · `⚑` escalate · `⇒` calls workflow · `◉` end

```
● target / opportunity (IP flag or Owner request)
  └─► [Set baseline (sourced) — Cost Reduction]
  └─► [Build should-cost — Cost Reduction]
  └─► [Identify levers — Cost Reduction]
  └─► ◇G1 <lever needs spec change?>
        ├─ yes ─► ⇒ engineering_change.md ─┐
        └─ no ──────────────────────────────┤
  └─► ◇G2 <which lever?>
        ├─ negotiate ─► ⇒ price_negotiation.md
        └─ resource ──► ⇒ rfq.md
  └─► [Build savings case vs baseline (D2) — Cost Reduction]
  └─► ◇G3 <validated against baseline?>
        ├─ no ──► ⚑ re-task (no claim)
        └─ yes ─► ⚑ L3 Human Owner (approve price change)
                    └─► [Book saving ⇒ sap.md + update register — SAP Purch/Cost Reduction] ──► ◉ realized
```

## 1. Purpose
Deliver measurable, validated, realized savings with defensible should-cost logic.

## 2. Inputs

| Input | Source |
|-------|--------|
| Part spec & volume (EAU) | `../company/`, `/projects` |
| Cost models & rates | `../knowledge/cost/` *(TBD)* |
| Price history / quotes | `/rfq`, `/cost_down` |
| Opportunity flag | Procurement Analytics (IP) |

## 3. Required AI Employees

| Employee | Dept | Role in this flow |
|----------|------|-------------------|
| Cost Reduction | CC | Owner — should-cost, levers, savings case |
| Procurement Analytics | IP | Opportunity, baseline data, savings tracking |
| Technical Purchasing | SE | Feasibility of VA/VE spec changes |
| RFQ Management | CC | Execute negotiation / re-quote |
| SAP Purchasing | TS | Book realized saving |

## 4. Decision Gates

| Gate | Condition | Yes → | No → |
|------|-----------|-------|------|
| G1 | Lever needs spec change? | ⇒ [engineering_change.md](engineering_change.md) | Continue |
| G2 | Which lever? | negotiate ⇒ [price_negotiation.md](price_negotiation.md) | resource ⇒ [rfq.md](rfq.md) |
| G3 | Saving validated vs baseline? | ⚑ Human Owner (realize) | Re-task, no claim |

## 5. Outputs

| Output | Destination |
|--------|-------------|
| Should-cost model | `/cost_down/<id>/should-cost.md` |
| VA/VE idea log | `/cost_down/<id>/ideas.md` |
| Validated savings case | `/cost_down/<id>/savings-case.md` |
| Savings register update | `/cost_down/savings-register.md`, `/dashboard` |

## 6. Escalation Rules
- **L1 (CC head):** lever choice disputes, baseline data gaps.
- **L2 (Procurement Lead):** cross-dept conflict (e.g. quality vs cost).
- **L3 (Human Owner):** price change/realization (D3); spec change; material quality/continuity risk.

## 7. KPI

| KPI | Target |
|-----|--------|
| Validated savings (THB / %) | TBD |
| Idea → realization rate | TBD |
| Should-cost accuracy vs actual | TBD |

## 8. Checklist

- [ ] Baseline price × volume sourced (not `TBD`).
- [ ] Should-cost rates cited; estimates marked `EST`.
- [ ] Spec-change levers routed to engineering_change.
- [ ] Saving validated against baseline before claiming.
- [ ] Quality/continuity unaffected (SM/SE sign-off if at risk).
- [ ] Human Owner approval before realization; booked in SAP.

## 9. Common Mistakes

- ❌ Claiming a saving not validated against a real baseline.
- ❌ Hidden quality loss to hit a cost target.
- ❌ Changing spec without engineering_change + approval.
- ❌ Double-counting savings across cases (no single register).
- ❌ Should-cost built on assumed, uncited rates.

## 10. Automation Opportunities

- ⚙ Pull baseline price/volume automatically from SAP/`/rfq`.
- ⚙ Should-cost calculator templated from process rates.
- ⚙ Auto-reconcile validated vs realized in the savings register.
- ⚙ IP auto-flags parts above should-cost threshold.
