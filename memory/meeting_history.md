---
id: meeting-history
title: Meeting & Decision History (Log)
type: register-native
status: active
updated: 2026-06-25
---

# Meeting & Decision History (Log)

> Chronological log of reviews, decisions, and escalations across the
> organization. **Memory-native: this log is the source of truth for "what was
> decided and when."**

## What This Is
A durable, append-only record of organizational decision points — Chief of Staff
syntheses, cross-department reviews, escalations, and Human Owner approvals. The
*detailed* artifacts live in their owning records; this is the timeline that ties
them together for recall.

## Schema (newest on top)

| Date | Type | Participants | Topic | Decision | Class | Record |
|------|------|--------------|-------|----------|-------|--------|
| _2026-06-25_ | _review_ | _Chief of Staff, …_ | _example_ | _example_ | _D0–D4_ | _link_ |

> No decisions logged yet.

## Conventions
- Append newest entry on top; never edit or delete history (correct by adding).
- `Type`: review / decision / escalation / approval.
- `Class`: decision class D0–D4 ([decision-framework](../company/decision-framework.md)).
- `Record`: link to the owning record where the decision is detailed.
- Every D3/D4 approval by the Human Owner is logged here.

## Links
- Decision rules: [`decision-framework`](../company/decision-framework.md)
- Escalations: [`escalation-rules`](../company/organization/escalation-rules.md)
- Projects: [project_history.md](project_history.md)
