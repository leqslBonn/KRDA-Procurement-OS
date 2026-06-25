# /dashboard

The management view: KPIs, spend visibility, and reporting. Owned by the
**Procurement Analytics** agent. Reads from records; does not own source data.

> มุมมองผู้บริหาร — KPI ภาพรวมการใช้จ่าย และรายงาน

## What Lives Here

- KPI snapshots and trends (savings, cycle time, OTD, quality, spend coverage).
- Spend summaries (by category, supplier, plant).
- Periodic reports.

## Principle

The dashboard **aggregates** from owning records — it never becomes a second
source of truth. Every figure traces back to `/projects`, `/rfq`, `/cost_down`,
`/suppliers`, or SAP records.

## Structure (grow as needed)

```
/dashboard
  kpis.md            ← KPI definitions live in /knowledge; values summarized here
  spend-summary.md   ← rolled-up spend view
  reports/           ← periodic reports (YYYY-Qn / YYYY-MM)
```

## Conventions

- KPI **definitions** live in `/knowledge/taxonomy`; the dashboard shows values.
- Date every snapshot; keep history in `reports/`.
- No unsourced numbers.
