---
id: memory-engine
title: Memory Engine — Auto-Update on Completion
owner: Chief of Staff / Procurement Automation
status: active
updated: 2026-06-25
---

# Memory Engine — Auto-Update on Completion

> When a project, RFQ, cost-down, audit, negotiation, or simulation **completes**,
> the Memory Engine pushes updates to every relevant register so memory stays the
> single source of truth — automatically, not manually.

This operationalizes **stage 12 (Archive Knowledge)** of the
[Workflow Engine](../workflows/ENGINE.md), under the
[memory architecture](architecture.md) routing rules.

## Trigger

Any record reaching `status: archived` / `realized` / `closed`, or any
[simulation](../simulation/README.md) run finishing.

## Update Map (what fires where)

| On completion of… | Updates |
|-------------------|---------|
| Supplier onboarding / audit | `supplier_database`, scorecard, `risk_database` |
| RFQ / award | `rfq_database`, `project_history`, `cost_database` (if target), `meeting_history` (award) |
| Cost-down realized | `cost_database`, `/cost_down/savings-register.md`, `meeting_history` |
| Negotiation closed | `negotiation_history`, `cost_database`, `meeting_history` |
| Contract / NDA signed | `contract_database`, `/schedule` (expiry), `meeting_history` |
| Engineering change cut-in | `project_history`, `commodity_database`, `risk_database` |
| Any project | `project_history`, **`lessons_learned`** |
| Simulation run | `lessons_learned`, `/improvement` action items |

## Rules

1. **Dedup-first** (per [architecture §8](architecture.md)): search before write;
   update the existing row, never create a duplicate.
2. **Link, never copy** — registers hold metadata + links to the canonical record.
3. **Always capture a lesson.** Every completion appends to
   [lessons_learned.md](lessons_learned.md), even if "all nominal."
4. **Numbers reconcile.** Conflicting figures → Procurement Analytics reconciles to
   source ([architecture §9](architecture.md)).
5. **One pass, all registers.** A completion updates *all* mapped registers in one
   archival step so they never drift.

## Lesson Capture (minimum)

```markdown
- Date · Source record (link) · What happened · What worked / failed ·
  Framework/knowledge gap? · Action (→ /improvement) · Reusable lesson
```

## Automation

This routine is a prime target for [Procurement Automation](../agents/procurement-automation.md):
the archival step should fire register updates from a record's status change. Until
automated, the Chief of Staff performs it at stage 12. Never let archival be skipped.
