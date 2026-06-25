---
id: departments
title: Departments
owner: Procurement Lead
status: active
updated: 2026-06-25
---

# Departments

The KRDA AI Procurement Department is organized into **one office and five
operating departments**. Each groups existing role charters
([`/agents`](../../agents/index.md)) under a single head. Departments define
*what each group is responsible for*; role charters define *how each role works*.

> หกหน่วยงาน: สำนักงาน Lead + 5 department ปฏิบัติการ — แต่ละหน่วยมีหัวหน้าเดียว

---

## Department Roster

| Code | Department | Member roles | Head |
|------|------------|--------------|------|
| OPL | Office of the Procurement Lead | Procurement Lead | Procurement Lead |
| SE | Sourcing & Engineering | Strategic Sourcing, Technical Purchasing | Strategic Sourcing |
| SM | Supplier Management | Supplier Development | Supplier Development |
| CC | Commercial & Cost | RFQ Management, Cost Reduction | RFQ Management |
| TS | Transactions & Systems | SAP Purchasing, Procurement Automation | SAP Purchasing |
| IP | Intelligence & Performance | Procurement Analytics | Procurement Analytics |

---

## OPL — Office of the Procurement Lead

- **Purpose:** single entry point; coordinate the organization; protect the
  commitment gate.
- **Responsible for:** intake & routing, cross-department coordination,
  prioritization, escalation to the Human Owner, the `/schedule`.
- **Owns records:** routing/decision log in `/projects`; priorities in `/schedule`.
- **Boundary:** does not perform domain work — it routes it.
- **Head:** Procurement Lead → reports to **Human Owner**.

## SE — Sourcing & Engineering

- **Purpose:** decide *what* to buy and *from whom*, technically correct.
- **Member roles:** Strategic Sourcing (where/whom, category strategy),
  Technical Purchasing (spec, drawing, qualification).
- **Responsible for:** category strategy, supplier selection shortlists,
  technical specs and acceptance criteria, new-part qualification.
- **Owns records:** category strategies & specs in `/projects`; qualification
  results into `/suppliers`.
- **Boundary:** does not run quotes (→ CC), develop suppliers (→ SM), or post
  transactions (→ TS).
- **Head:** Strategic Sourcing → reports to Procurement Lead.

## SM — Supplier Management

- **Purpose:** make the supply base stronger and reliable over time.
- **Member roles:** Supplier Development.
- **Responsible for:** supplier assessment & audits, development plans / CAPA,
  performance scorecards, qualification-status maintenance.
- **Owns records:** supplier profiles, scorecards, audits in `/suppliers`.
- **Boundary:** does not select the sourcing winner (→ SE) or negotiate price (→ CC).
- **Head:** Supplier Development → reports to Procurement Lead.

## CC — Commercial & Cost

- **Purpose:** get competitive, fair pricing and prove savings.
- **Member roles:** RFQ Management (quotes, comparison, award rec),
  Cost Reduction (should-cost, VA/VE, savings).
- **Responsible for:** RFQ packages & bid tabs, award recommendations,
  should-cost models, validated savings cases, negotiation preparation.
- **Owns records:** RFQs in `/rfq`; savings in `/cost_down`.
- **Boundary:** defines no specs (→ SE), posts no PO (→ TS), signs no contract
  (→ Human Owner via OPL).
- **Head:** RFQ Management → reports to Procurement Lead.

## TS — Transactions & Systems

- **Purpose:** turn approved decisions into clean transactions and remove manual toil.
- **Member roles:** SAP Purchasing (PR/PO, master data), Procurement Automation
  (reusable workflows, integration, scheduling).
- **Responsible for:** SAP-ready PR/PO content, master-data hygiene, automation
  design, scheduled tasks.
- **Owns records:** transaction records in `/projects`; workflows in `/workflows`;
  schedule entries in `/schedule`.
- **Boundary:** makes no award (→ CC); never posts a real transaction without
  Human Owner authorization.
- **Head:** SAP Purchasing → reports to Procurement Lead.

## IP — Intelligence & Performance

- **Purpose:** give the organization a clear, current picture and find opportunity.
- **Member roles:** Procurement Analytics.
- **Responsible for:** spend analysis, KPI definition & tracking, reporting,
  opportunity & risk flags.
- **Owns records:** analyses & reports in `/dashboard`; KPI definitions live in
  `/knowledge/taxonomy` and are referenced, not copied.
- **Boundary:** acts on no insight itself — routes it to the owning department.
- **Head:** Procurement Analytics → reports to Procurement Lead.

---

## Cross-Department Value Flow (orientation only — not a workflow)

```
SE (what/whom + spec) ──► CC (quote + cost) ──► [Human Owner approves]
        ▲      │                 │
        │      ▼                 ▼
       SM (supplier capability)  TS (PR/PO + automation)
        └──────────────► IP (spend, KPI, opportunity) ──► feeds all
```

Detailed reporting and hand-offs: [reporting-lines.md](reporting-lines.md).
