# /agents

The AI **employees** of the KRDA Procurement Department. Each is defined by a
full **employee definition** — a single Markdown file covering its purpose,
responsibilities, inputs, outputs, decision authority, escalation, routines, KPIs,
communication, knowledge scope, reasoning style, limitations, and success metrics.

> นิยาม "พนักงาน AI" แต่ละตัว — หนึ่งไฟล์ = หนึ่งพนักงาน หน้าที่ชัด ครบ 14 หัวข้อ

## Employee Definition — 14 sections

Every employee file contains, in order:
**1** Purpose · **2** Responsibilities · **3** Inputs · **4** Outputs ·
**5** Decision Authority · **6** Escalation Path · **7** Daily Routine ·
**8** Weekly Routine · **9** KPI · **10** Communication Protocol ·
**11** Knowledge Scope · **12** Expected Reasoning Style · **13** Limitations ·
**14** Success Metrics.

## How Employees Work

- One employee per file. No overlapping ownership.
- Each belongs to a **department** (OPL/SE/SM/CC/TS/IP) — see
  [`../company/organization/`](../company/organization/README.md).
- Decision authority maps to classes **D0–D4**
  ([decision-framework](../company/decision-framework.md)); escalation to **L0–L3**
  ([escalation-rules](../company/organization/escalation-rules.md)).
- Employees execute workflows (`/workflows`) using templates (`/templates`) and
  knowledge (`/knowledge`); they never duplicate another's job — they **hand off**.
- The **Procurement Lead** routes requests and guards the commitment gate.

## Files

| File | Purpose |
|------|---------|
| [index.md](index.md) | Registry of all employees (start here). |
| [_TEMPLATE.md](_TEMPLATE.md) | 14-section employee-definition template. |
| `procurement-lead.md` | Orchestrator / router. |
| `technical-purchasing.md` | Parts, specs, qualification. |
| `strategic-sourcing.md` | Category strategy, supplier selection. |
| `supplier-development.md` | Supplier capability & quality. |
| `cost-reduction.md` | Should-cost, VA/VE, savings. |
| `rfq-management.md` | Quotes, comparison, awards. |
| `sap-purchasing.md` | PR/PO, master data, transactions. |
| `procurement-analytics.md` | Spend, KPI, reporting. |
| `procurement-automation.md` | Process automation & integration. |

## Adding an Employee

1. Copy [_TEMPLATE.md](_TEMPLATE.md) to `your-employee.md`.
2. Fill all 14 sections; assign a department; keep scope non-overlapping.
3. Add a row to [index.md](index.md) and to the relevant department in
   [`../company/organization/departments.md`](../company/organization/departments.md).
