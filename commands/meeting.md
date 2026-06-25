---
id: cmd-meeting
title: /meeting
type: command
trigger: "/meeting <topic>"
dispatches_to: []
owner: Chief of Staff
status: active
updated: 2026-06-25
---

# /meeting

> Convene a review/decision across the relevant employees and record the outcome
> in the decision log.

## Purpose
Capture a decision, review, or approval as a durable record — the organization's
memory of "what was decided and why."

## Invocation

```
/meeting <topic> [employees] [class]
```

| Argument | Required | Meaning |
|----------|----------|---------|
| topic | yes | What is being decided/reviewed |
| employees | no | Who to consult; else Chief of Staff selects relevant depts |
| class | no | Decision class D0–D4 |

## Preconditions
- The topic and the decision to be made are stated.

## What It Does (dispatch)
1. [Chief of Staff] Frame the decision; classify D0–D4; pick relevant departments.
2. [Selected employees] Provide inputs (independent, evidence-based — no domination).
3. [Chief of Staff] Detect conflicts; synthesize; decide or escalate.
4. [Chief of Staff] If commitment (D3/D4) → route to Human Owner.
5. [Chief of Staff] Log the decision in `meeting_history.md`.

## Memory Routing
Per [architecture.md](../memory/architecture.md).
- Canonical record: `../memory/meeting_history.md` (native register — append on top)
- Stable ID: date + linked record
- Cross-link: the owning record (`/projects`, `/rfq`, ...) where detail lives

## Outputs

| Output | Destination |
|--------|-------------|
| Decision log entry | `../memory/meeting_history.md` |
| Detail (if any) | owning record |

## Approval Gates
- Any D3/D4 decision is logged as **pending Human Owner** until approved.

## Example
```
/meeting "award PN-12345 to Supplier B" class=D3
```

## Links
- Decision log: [meeting_history.md](../memory/meeting_history.md)
- Doctrine: [chief-of-staff.md](../company/chief-of-staff.md)
- Decision rules: [decision-framework.md](../company/decision-framework.md)
