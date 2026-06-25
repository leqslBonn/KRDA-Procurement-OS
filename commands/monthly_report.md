---
id: cmd-monthly-report
title: /monthly_report
type: command
trigger: "/monthly_report [month]"
dispatches_to: [../skills/executive_report.md, ../skills/presentation.md]
owner: Procurement Analytics (IP)
status: active
updated: 2026-06-25
---

# /monthly_report

> Produce the monthly executive review: spend & savings performance, supplier
> health, risk posture, and progress vs targets.

## Purpose
Give the Human Owner a strategic monthly picture — trends and outcomes, not just
this week's activity — to steer the function.

## Invocation

```
/monthly_report [month]
```

| Argument | Required | Meaning |
|----------|----------|---------|
| month | no | Target month (default: last), `YYYY-MM` |

## Preconditions
- Month's records closed/updated; savings validated where claimed.

## What It Does (dispatch)
1. [Chief of Staff] Trigger; set scope = the month.
2. [Procurement Analytics] Spend by category/supplier; KPI trends vs target.
3. [Procurement Analytics] Savings realized (`/cost_down/savings-register.md`),
   supplier performance, risk posture (`risk_database`).
4. [Analytics/Chief of Staff] Assemble exec review via
   [executive_report](../skills/executive_report.md) + deck via [presentation](../skills/presentation.md).
5. [Chief of Staff] Highlight strategic decisions and exceptions for the Human Owner.

## Memory Routing
Per [architecture.md](../memory/architecture.md).
- Canonical record: `/dashboard/reports/<YYYY-MM>-monthly.md`
- Aggregates from registers and the savings register — links only, no copied data.

## Outputs

| Output | Destination |
|--------|-------------|
| Monthly executive review (+ deck) | `/dashboard/reports/` |

## Approval Gates
- Informational/strategic. Any commitment surfaced → Human Owner (D3/D4).

## Example
```
/monthly_report 2026-05
```

## Links
- Skills: [executive_report.md](../skills/executive_report.md), [presentation.md](../skills/presentation.md)
- Source: [`/dashboard`](../dashboard/README.md), `/cost_down/savings-register.md`
- Weekly: [weekly_report.md](weekly_report.md)
