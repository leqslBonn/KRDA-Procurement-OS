# /improvement — Continuous Improvement System

Every week the AI company **reviews itself**: mistakes, missing knowledge, poor
decisions, workflow gaps, automation opportunities, and knowledge gaps — then
generates action plans. This is how the organization compounds.

> ระบบพัฒนาต่อเนื่อง — ทุกสัปดาห์บริษัท AI ทบทวนตัวเอง แล้วสร้าง action plan

## Inputs (where the signal comes from)

| Source | Signal |
|--------|--------|
| [lessons_learned](../memory/lessons_learned.md) | What worked / failed |
| [simulation](../simulation/README.md) | Rubric scores, weak frameworks |
| [KPI system](../dashboard/kpis.md) | Off-target metrics |
| [risk_database](../memory/risk_database.md) | Recurring risks |
| [meeting_history](../memory/meeting_history.md) | Decisions revisited |

## The Weekly Review

```
collect signals ─► classify (6 buckets) ─► root-cause ─► action plan ─► assign owner
              ─► improve the SYSTEM (brain/workflow/knowledge) before adding content
```

Six review buckets (per STEP 9):
1. **Mistakes** — what went wrong, why.
2. **Missing Knowledge** — `/knowledge` gaps found.
3. **Poor Decisions** — where a framework gave a weak result.
4. **Workflow Improvements** — process friction / gaps.
5. **Automation Opportunities** — repetitive toil to automate.
6. **Knowledge Gaps** — `TBD`s blocking work.

## Outputs

- A dated review using [_TEMPLATE.md](_TEMPLATE.md) → `reviews/<YYYY-Www>.md`.
- Action items appended to [ACTIONS.md](ACTIONS.md) with owner + due.
- System changes (brain/workflow/knowledge edits) — **improve before adding content**.

## Principle

> Always improve the system before adding new content. When a weakness is found,
> refactor the framework, workflow, or knowledge — don't patch around it.

## Files

| File | Purpose |
|------|---------|
| [_TEMPLATE.md](_TEMPLATE.md) | Weekly self-review template (6 buckets). |
| [ACTIONS.md](ACTIONS.md) | Rolling action log (owner, due, status). |
| `reviews/<YYYY-Www>.md` | Dated weekly reviews. |

## Cadence
Run weekly via [/weekly_report](../commands/weekly_report.md) (improvement section)
or a scheduled task in [/schedule](../schedule/README.md).
