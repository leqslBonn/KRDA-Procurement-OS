---
id: wf-engineering-change
title: Engineering Change (Purchasing Impact)
type: workflow
owner: Technical Purchasing (SE)
status: active
updated: 2026-06-25
---

# Engineering Change (Purchasing Impact)

> Assess and execute the purchasing impact of an engineering change (ECN) — spec,
> qualification, cost, supplier, transactions. Touches every department.

## Flow (BPMN-like)

Legend (canonical: [README](README.md#bpmn-notation)):
`●` start · `[task — Role]` · `◇Gn` gateway · `⚑` escalate · `⇒` calls workflow · `◉` end

```
● ECN / VA-VE spec change
  └─► [Assess technical impact — Tech Purchasing]
  └─► [Supplier impact — Supplier Dev] ∥ [Cost impact — Cost Reduction] ∥ [Sourcing impact — Strat Sourcing] ∥ [Txn impact — SAP Purch]
  └─► [Consolidate impact + cut-in plan (D2) — Tech Purchasing]
  └─► ⚑ L3 Human Owner (approve change/cut-in)
  └─► ◇G1 <re-qualification needed?>
        ├─ yes ─► ⇒ supplier_audit.md
        └─ no ──► continue
  └─► ◇G2 <price impact?>
        ├─ yes ─► ⇒ price_negotiation.md
        └─ no ──► continue
  └─► ◇G3 <new supplier needed?>
        ├─ yes ─► ⇒ supplier_selection.md
        └─ no ──► [Update spec/master + cut-in ⇒ sap.md — Tech Purch/SAP] ──► ◉ change cut in
```

## 1. Purpose
Make engineering changes buyable: assess full purchasing impact and cut in safely.

## 2. Inputs

| Input | Source |
|-------|--------|
| ECN / change request | Engineering / `/projects` |
| Current spec & drawing | `../templates/spec-sheet.md` → project copy |
| Affected part & supplier | `/suppliers`, `/projects` |
| Standards | `../knowledge/standards/` *(TBD)* |

## 3. Required AI Employees

| Employee | Dept | Role in this flow |
|----------|------|-------------------|
| Technical Purchasing | SE | Owner — technical impact, consolidation, cut-in |
| Supplier Development | SM | Supplier capability/re-qual impact |
| Cost Reduction | CC | Price/tooling/obsolescence impact |
| Strategic Sourcing | SE | Make/buy & source-list impact |
| SAP Purchasing | TS | Master data & open-PO impact |
| Procurement Lead | OPL | Route cut-in approval |

## 4. Decision Gates

| Gate | Condition | Yes → | No → |
|------|-----------|-------|------|
| G1 | Re-qualification needed? | ⇒ [supplier_audit.md](supplier_audit.md) | Continue |
| G2 | Price impact? | ⇒ [price_negotiation.md](price_negotiation.md) | Continue |
| G3 | New supplier needed? | ⇒ [supplier_selection.md](supplier_selection.md) | Update & cut in ⇒ [sap.md](sap.md) |

## 5. Outputs

| Output | Destination |
|--------|-------------|
| Change impact assessment (all depts) | `/projects/<id>/` |
| Updated controlled spec sheet | `/projects/<id>/` |
| Cut-in plan & approval record | `/projects/<id>/` |

## 6. Escalation Rules
- **L1 (SE head):** impact-assessment disputes.
- **L2 (Procurement Lead):** cross-dept disagreement on cut-in timing.
- **L3 (Human Owner):** change execution / cut-in (D3); controlled-spec change; obsolescence cost.

## 7. KPI

| KPI | Target |
|-----|--------|
| Change cut-in lead time | TBD |
| Obsolescence cost vs plan | TBD |
| Cut-ins without quality escape | 100% |

## 8. Checklist

- [ ] Change described old→new with reason.
- [ ] Impact assessed by all relevant depts (none skipped).
- [ ] Re-qualification routed if needed.
- [ ] Price/obsolescence quantified.
- [ ] Human Owner approved cut-in.
- [ ] Spec controlled & master data updated before cut-in.

## 9. Common Mistakes

- ❌ Cutting in before spec control / re-qualification.
- ❌ Skipping a department's impact assessment.
- ❌ Ignoring old-stock obsolescence cost.
- ❌ Letting a price increase slip in unapproved.
- ❌ Updating drawings without engineering + Human Owner authorization.

## 10. Automation Opportunities

- ⚙ Impact-assessment fan-out to all depts from one ECN record.
- ⚙ Auto-detect affected open POs / master data.
- ⚙ Old-stock obsolescence calculator.
- ⚙ Cut-in checklist gating before SAP update.
