---
id: org-chart
title: Organization Chart
owner: Procurement Lead
status: active
updated: 2026-06-25
---

# Organization Chart

The roles of the KRDA AI Procurement Department, their reporting lines, and their
authority. This is the **canonical authority chart**. Detailed role definitions
live as charters in [`/agents`](../agents/index.md); the departmental grouping,
reporting matrix, escalation, and communication rules live in
[`organization/`](organization/README.md). This document defines *authority*, and
links to those for *detail* — it does not duplicate them.

> ผังอำนาจของแผนกจัดซื้อ AI (canonical) — นิยามบทบาทอยู่ใน /agents, การจัดกลุ่ม
> department + reporting + escalation + communication อยู่ใน organization/

---

## 1. Authority Hierarchy

```
                        ┌──────────────────────┐
                        │     HUMAN OWNER       │  ← ultimate authority,
                        │  (Wongsakorn / KRDA)  │     all D3/D4 commitments
                        └──────────┬───────────┘
                                   │ approves commitments, sets direction
                        ┌──────────▼───────────┐
                        │   CHIEF OF STAFF      │  ← manages the cycle, synthesizes
                        │   (OPL · executive)   │     one executive recommendation
                        └──────────┬───────────┘
                                   │ manages via
                        ┌──────────▼───────────┐
                        │   PROCUREMENT LEAD    │  ← routing, coordination,
                        │    (Orchestrator)     │     escalation
                        └──────────┬───────────┘
        ┌───────────┬─────────────┼─────────────┬───────────────┐
        ▼           ▼             ▼             ▼               ▼
  ┌──────────┐┌──────────┐┌────────────┐┌────────────┐┌──────────────┐
  │Technical ││Strategic ││ Supplier   ││    RFQ      ││     SAP      │
  │Purchasing││ Sourcing ││Development ││ Management  ││  Purchasing  │
  └──────────┘└──────────┘└────────────┘└────────────┘└──────────────┘
        └─────────► COST REDUCTION ◄──────┘             │
                                                         ▼
                          ┌──────────────────┐   ┌──────────────┐
                          │   Procurement    │◄──│ Procurement  │
                          │   Analytics      │   │  Automation  │
                          └──────────────────┘   └──────────────┘
```

## 2. Governance Layers

| Layer | Who | Role |
|-------|-----|------|
| **Authority** | Human Owner | Sets direction; approves all commitments (D3) and constitutional changes (D4). |
| **Executive** | Chief of Staff | Manages the task cycle; balances all departments; produces one evidence-based recommendation. See [chief-of-staff.md](chief-of-staff.md). |
| **Coordination** | Procurement Lead | Single entry point; routes work; escalates; owns priorities & schedule. |
| **Execution** | 8 specialist roles | Do the domain work within charter; hand off across boundaries. |

## 3. Roles & Departments

Roles are grouped into **one office and five departments**. Each department has a
single head (an existing role) reporting to the Procurement Lead.

| Role | Department | Core responsibility | Dept head? |
|------|-----------|---------------------|:----------:|
| Procurement Lead | OPL — Office of the Lead | Routing, coordination, escalation | ● |
| Strategic Sourcing | SE — Sourcing & Engineering | Category strategy, supplier selection | ● |
| Technical Purchasing | SE — Sourcing & Engineering | Specs, drawings, qualification | |
| Supplier Development | SM — Supplier Management | Capability, quality, audits | ● |
| RFQ Management | CC — Commercial & Cost | Quotes, comparison, award rec | ● |
| Cost Reduction | CC — Commercial & Cost | Should-cost, VA/VE, savings | |
| SAP Purchasing | TS — Transactions & Systems | PR/PO, master data | ● |
| Procurement Automation | TS — Transactions & Systems | Automation, integration | |
| Procurement Analytics | IP — Intelligence & Performance | Spend, KPI, reporting | ● |

> - Department design & responsibilities: [organization/departments.md](organization/departments.md)
> - Canonical reporting matrix, RACI & hand-off map: [organization/reporting-lines.md](organization/reporting-lines.md)
> - Per-role inputs/outputs/guardrails: charters in [`/agents`](../agents/index.md)
>
> These are linked, not duplicated here.

## 4. Spans of Authority (what each layer may decide)

| Layer | May decide (per [Decision Framework](decision-framework.md)) |
|-------|--------------------------------------------------------------|
| Specialist roles | D0 operational, D2 recommendations (within charter) |
| Procurement Lead | D1 coordination, routing, prioritization |
| Human Owner | **D3 commitments, D4 constitutional changes** |

## 5. Escalation Path

```
L0 member role ──► L1 dept head ──► L2 Procurement Lead ──► L3 Human Owner
   (in-charter)     (intra-dept)      (cross-dept)           (commitment / exception)
```

Anything implying a financial, legal, or contractual commitment, a single-source
designation, or a principle exception travels this path to the Human Owner. Full
triggers, levels, and recording: [organization/escalation-rules.md](organization/escalation-rules.md).
Communication channels & message format: [organization/communication-rules.md](organization/communication-rules.md).

## 6. Growth Rule

New roles are added only when a genuine, non-overlapping responsibility exists.
Add a charter in [`/agents`](../agents/_TEMPLATE.md), then add the role here.
Never split one responsibility across two roles.
