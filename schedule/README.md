# /schedule

Timing and recurrence: the procurement calendar and recurring tasks. Set up by
the **Procurement Lead** and **Procurement Automation** agents.

> ตารางเวลาและงานประจำ — ปฏิทินจัดซื้อและงานที่ทำซ้ำตามรอบ

## What Lives Here

- Recurring procurement tasks (e.g. quarterly supplier scorecards, monthly spend
  report, contract renewal checks).
- Key dates and deadlines (RFQ due dates, contract expiries, audit cycles).

## Structure

```
/schedule
  recurring.md   ← recurring tasks (cadence, owner agent, trigger)
  calendar.md    ← upcoming dated deadlines
```

## Conventions

- Each recurring task names a **cadence**, an **owner agent**, and the
  **workflow** it triggers.
- A schedule entry triggers work; it does not duplicate the work's records.
- Contract expiries link to `/contracts`; RFQ due dates link to `/rfq`.

## Example Recurring Tasks (to define)

| Task | Cadence | Owner agent | Triggers |
|------|---------|-------------|----------|
| Supplier scorecard refresh | Quarterly | Supplier Development | scorecard workflow |
| Spend & KPI report | Monthly | Procurement Analytics | reporting workflow |
| Contract renewal review | Monthly | Procurement Lead | contract review |
