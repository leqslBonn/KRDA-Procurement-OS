---
id: cmd-weekly-report
title: /weekly_report
type: command
trigger: "/weekly_report [week]"
dispatches_to: [../skills/executive_report.md, ../skills/presentation.md]
owner: Procurement Analytics (IP)
status: active
updated: 2026-06-25
---

# /weekly_report

> Produce the weekly procurement status: spend, KPIs, active RFQs/cost-downs,
> risks, and decisions due.

## Purpose
Give the Human Owner a fast, sourced weekly picture and a short list of what needs
attention.

## Invocation

```
/weekly_report [week]
```

| Argument | Required | Meaning |
|----------|----------|---------|
| week | no | Target week (default: current), `YYYY-Www` |

## Preconditions
- Records updated for the week (RFQs, cost-downs, suppliers, decisions).

## What It Does (dispatch)
1. [Chief of Staff] Trigger; set scope = the week.
2. [Procurement Analytics] Pull KPIs & spend from `/dashboard` and registers.
3. [Procurement Analytics] Summarize: active RFQs (`rfq_database`), cost-downs
   (`cost_database`), open risks (`risk_database`), decisions due (`meeting_history`).
4. [Analytics/Chief of Staff] Assemble via [executive_report](../skills/executive_report.md);
   optional deck via [presentation](../skills/presentation.md).
5. [Chief of Staff] Flag items needing a Human Owner decision.

## Memory Routing
Per [architecture.md](../memory/architecture.md).
- Canonical record: `/dashboard/reports/<YYYY-Www>-weekly.md`
- Aggregates from registers — **no copied source data**, links only.

## Outputs

| Output | Destination |
|--------|-------------|
| Weekly report (+ optional deck) | `/dashboard/reports/` |

## Approval Gates
- Informational. Any flagged commitment → Human Owner (D3).

## Example
```
/weekly_report 2026-W26
```

## Links
- Skills: [executive_report.md](../skills/executive_report.md), [presentation.md](../skills/presentation.md)
- Source: [`/dashboard`](../dashboard/README.md)
- Monthly roll-up: [monthly_report.md](monthly_report.md)
