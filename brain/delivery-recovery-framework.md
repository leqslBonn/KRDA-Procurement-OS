---
id: framework-delivery-recovery
title: Delivery Recovery Framework
type: framework
used_by: [../agents/supplier-development.md, ../agents/procurement-lead.md]
status: active
updated: 2026-06-25
---

# Delivery Recovery Framework

> The logic for recovering a late or short delivery and protecting the line.

## Purpose
Respond to a delivery miss fast — contain impact, recover supply, prevent recurrence.

## When to Use
On any OTD miss / shortage signal affecting production.

## Decision Inputs

| Input | Source |
|-------|--------|
| Shortage / late signal | `/dashboard`, Production |
| Supplier status & capacity | `/suppliers` |
| Demand / line need | `../company/`, Production |

## Framework (recovery ladder)

| Stage | Action |
|-------|--------|
| 1. Contain | Quantify gap, line risk date, safety stock on hand |
| 2. Expedite | Partial ship, air freight, reschedule with supplier |
| 3. Alternate | Second source / qualified alt (if exists) |
| 4. Re-plan | Adjust production sequence with Production |
| 5. Root cause | Why late? Capacity/quality/logistics |
| 6. Prevent | CAPA, buffer policy, supplier development |

## Decision Rule
- Triage by **line-down risk** (hours to stockout) × volume impact.
- Escalate severity: minor → supplier; line-down risk → **L3 Human Owner**.
- Expedite cost vs line-down cost — choose lower total impact.

## Escalation / Commitment Gate
- Expedite spend / premium freight commitment = **D3 → Human Owner**.
- Logged in [risk_database](../memory/risk_database.md) + [meeting_history](../memory/meeting_history.md).

## Pitfalls
- ❌ Reacting without quantifying line-down risk.
- ❌ Premium freight without approval.
- ❌ Closing without root cause / prevention.

## Links
- Frameworks: [quality-escalation-framework](quality-escalation-framework.md), [supplier-risk-framework](supplier-risk-framework.md)
- Knowledge: `../knowledge/supplier-management/`, `../knowledge/procurement/`
