---
id: wf-vendor-project-control
title: Vendor Project Control (Owner-Side Outsourced Dev)
type: workflow
owner: Procurement Lead (OPL) + Technical Purchasing (SE)
status: active
updated: 2026-06-26
---

# Vendor Project Control (Owner-Side Outsourced Dev)

> KRDA hires a vendor to build (IoT / smart-farm / app); KRDA is the **owner/controller**.
> This is the end-to-end loop from defining the job to final acceptance — built so the
> owner stays in control via scope, milestones, acceptance, and money.

## Flow (BPMN-like)

Legend (canonical: [README](README.md#bpmn-notation)):
`●` start · `[task — Role]` · `◇Gn` gateway · `⚑` escalate · `⇒` calls workflow · `◉` end

```
● need a system built
  └─► [Write SOW / requirements — Tech Purchasing + owner]  (sow-requirement)
  └─► [Evaluate & select vendor — owner]  ⇒ startup-vendor-evaluation (scorecard)
  └─► ◇G1 <product proven?>
        ├─ no ─► [Run POC — owner]  (poc-evaluation)  ──► ◇G2 <POC pass?>
        │                                                   ├─ no ─► ⚑ stop / re-source
        │                                                   └─ yes ─┐
        └─ yes ─────────────────────────────────────────────────────┤
  └─► [Negotiate & secure terms — RFQ Mgmt]  (contract-terms-checklist)
  └─► ⚑ L3 Human Owner (sign contract: IP/data/escrow/milestones)
  └─► [Execute by milestone — vendor builds]
        └─► loop each milestone:
            [Acceptance test — owner]  (acceptance-checklist)
              └─► ◇G3 <milestone accepted?>
                    ├─ no ──► [Punch list → vendor fixes]  (no payment)
                    └─ yes ─► ⚑ Human Owner (release milestone payment, hold retention)
  └─► [Final acceptance + go-live — owner]
  └─► [Warranty period → release retention]  ──► ◉ project delivered & owned
```

## 1. Purpose
Let a non-building owner deliver an outsourced system on scope, cost, and quality —
while owning the IP/data and staying able to continue if the vendor fails.

## 2. Inputs

| Input | Source |
|-------|--------|
| Business/farm need | owner / stakeholders |
| SOW / requirements | [sow-requirement](../templates/sow-requirement.md) |
| Vendor proposals / pitches | the market |
| Budget band | [approval-matrix](../brain/approval-matrix.md) |

## 3. Required AI Employees

| Employee | Dept | Role in this flow |
|----------|------|-------------------|
| Technical Purchasing | SE | SOW, requirements, acceptance criteria |
| Strategic Sourcing | SE | Vendor landscape, selection |
| RFQ Management | CC | Negotiation, terms |
| Procurement Lead | OPL | Coordinate, route to Human Owner |
| Procurement Analytics | IP | TCO comparison |

## 4. Decision Gates

| Gate | Condition | Yes → | No → |
|------|-----------|-------|------|
| G1 | Product proven (not slideware)? | Negotiate terms | Run POC |
| G2 | POC passes success criteria? | Continue | Stop / re-source |
| G3 | Milestone accepted? | Release payment (retention held) | Punch list, no payment |

## 5. Outputs

| Output | Destination |
|--------|-------------|
| SOW, scorecards, TCO | `/projects/<id>/` |
| Contract (terms secured) | `/contracts/` |
| Acceptance records per milestone | `/projects/<id>/` |
| Delivered, KRDA-owned system | record + handover |

## 6. Escalation Rules
- **L1/L2:** scope disputes, punch-list disagreements, change requests.
- **L3 (Human Owner):** sign contract; every milestone **payment release**; accept scope
  changes with cost; vendor non-performance / termination.

## 7. KPI

| KPI | Target |
|-----|--------|
| Milestones accepted first-pass | TBD |
| Scope-creep / change-order cost | minimize |
| On-time, on-budget delivery | TBD |
| IP/data ownership secured | 100% |

## 8. Checklist
- [ ] SOW written with measurable acceptance criteria before selecting.
- [ ] Vendor scored; POC if unproven.
- [ ] Terms secured (IP, data, milestones, retention, escrow) before signing.
- [ ] Pay only on accepted milestones; retention held to warranty end.
- [ ] Every payment release approved by Human Owner.

## 9. Common Mistakes
- ❌ Selecting before a clear SOW (cost creep).
- ❌ Paying upfront / ahead of acceptance.
- ❌ Not securing IP/data ownership or escrow.
- ❌ Accepting on a demo instead of a real acceptance test.
- ❌ Letting scope changes in without a priced change order.

## 10. Automation Opportunities
- ⚙ Milestone/payment tracker tied to acceptance sign-off.
- ⚙ Auto-reminder for warranty end → release retention.
- ⚙ Scorecard → TCO → executive-summary auto-assembly.
