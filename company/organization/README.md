---
id: organization
title: AI Organization — Design
owner: Procurement Lead
status: active
updated: 2026-06-25
---

# AI Organization — Design

How the KRDA AI Procurement Department is organized into **departments**, how they
**report**, what they are **responsible** for, and the **escalation** and
**communication** rules that bind them.

This is the organizational layer. It groups the role charters in
[`/agents`](../../agents/index.md) into departments and sits under the
[Constitution](../constitution.md), [Decision Framework](../decision-framework.md),
and [Organization Chart](../org-chart.md).

> ชั้นการจัดองค์กร — จัดกลุ่ม agent เป็น department พร้อมสายบังคับบัญชา หน้าที่
> กฎ escalation และกฎการสื่อสาร อยู่ใต้ธรรมนูญและ decision framework

---

## Contents

| File | Purpose |
|------|---------|
| [departments.md](departments.md) | The departments, their members, heads, and responsibilities. |
| [reporting-lines.md](reporting-lines.md) | Canonical reporting matrix, RACI, and hand-off map. |
| [escalation-rules.md](escalation-rules.md) | When and how issues move up the chain. |
| [communication-rules.md](communication-rules.md) | How agents and departments communicate. |

---

## Organizational Chart (department view)

```
                       ┌───────────────────────┐
                       │      HUMAN OWNER       │
                       │   (Wongsakorn / KRDA)  │
                       └───────────┬───────────┘
                                   │
                       ┌───────────▼───────────┐
                       │  OFFICE OF THE LEAD    │   Dept: OPL
                       │   (Procurement Lead)   │
                       └───────────┬───────────┘
        ┌──────────────┬───────────┼───────────┬──────────────┐
        ▼              ▼           ▼           ▼              ▼
 ┌────────────┐ ┌────────────┐ ┌────────┐ ┌──────────┐ ┌────────────┐
 │ SOURCING & │ │  SUPPLIER  │ │COMMERC.│ │TRANSACT. │ │INTELLIGENCE│
 │ ENGINEERING│ │ MANAGEMENT │ │ & COST │ │& SYSTEMS │ │& PERFORM.  │
 │   (SE)     │ │   (SM)     │ │  (CC)  │ │  (TS)    │ │   (IP)     │
 ├────────────┤ ├────────────┤ ├────────┤ ├──────────┤ ├────────────┤
 │ Strategic  │ │ Supplier   │ │ RFQ    │ │ SAP      │ │ Procurement│
 │ Sourcing ◄─┤ │ Development│ │ Mgmt ◄─┤ │ Purch. ◄─┤ │ Analytics  │
 │ Technical  │ │  (head)    │ │ Cost   │ │ Procure. │ │  (head)    │
 │ Purchasing │ │            │ │ Reduct.│ │ Automat. │ │            │
 └────────────┘ └────────────┘ └────────┘ └──────────┘ └────────────┘
   head: Strat.   head: Supp.   head:RFQ   head: SAP    head: Analytics
   Sourcing       Development    Mgmt       Purchasing
```

`◄─` = department head (a coordinating role; an existing agent, not a new one).

---

## Design Rules

1. **Departments group responsibilities; they do not create new agents.** Each
   department is a set of existing role charters plus a designated head.
2. **One head per department.** The head coordinates the department and reports to
   the Procurement Lead. Members keep their own charter ownership.
3. **Authority is unchanged.** All commitment authority (D3/D4) remains with the
   Human Owner per the [Decision Framework](../decision-framework.md).
4. **Non-overlapping scope.** No responsibility lives in two departments.
5. **Grow by extension.** Add a role to a department, or add a department, only
   for a genuine non-overlapping need.
