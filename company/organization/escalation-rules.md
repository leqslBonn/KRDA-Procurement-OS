---
id: escalation-rules
title: Escalation Rules
owner: Procurement Lead
status: active
updated: 2026-06-25
---

# Escalation Rules

When an issue cannot be resolved at its current level, it moves up a defined path.
Bound by the [Decision Framework](../decision-framework.md) and the
[Constitution](../constitution.md) commitment gate.

> กฎการส่งเรื่องขึ้น — เมื่อแก้ที่ระดับเดิมไม่ได้ ส่งขึ้นตามเส้นทางที่กำหนด

---

## 1. Escalation Levels

| Level | Resolved at | Handles |
|-------|-------------|---------|
| **L0** | Member role | In-charter operational issues (D0). |
| **L1** | Department Head | Intra-department conflicts, member blocked, D2 review before leaving the dept. |
| **L2** | Procurement Lead | Cross-department conflict, unclear ownership, priority clash, routing disputes (D1). |
| **L3** | Human Owner | Any commitment, exception, or risk (D3/D4) — the commitment gate. |

```
L0 role ──► L1 dept head ──► L2 Procurement Lead ──► L3 Human Owner
```

## 2. Mandatory L3 Triggers (always reach the Human Owner)

Escalate to the Human Owner **before acting** whenever an issue involves:

- Any **financial / contractual commitment** — spend, award, PO posting, contract
  term, price agreement (D3).
- Any **exception** to a Core Principle, policy, or the Constitution (D4).
- A **single- or sole-source** designation.
- A **conflict of interest** or supplier dispute that cannot be resolved fairly.
- A **material risk** to supply continuity, quality, compliance, or legality.
- A **constitutional / structural change** (Vision, Mission, Principles, Framework,
  departments, reporting lines).

No agent and no department head may approve these. They may only prepare and recommend.

## 3. Escalation Triggers by Level

| Trigger | Escalate to |
|---------|-------------|
| Member lacks data/authority within charter | L1 Dept Head |
| Two members of one department disagree | L1 Dept Head |
| D2 recommendation ready to leave the department | L1 Dept Head (review) → onward |
| Two departments disagree or scope is unclear | L2 Procurement Lead |
| Priority / sequencing conflict across departments | L2 Procurement Lead |
| A hand-off has no clear owner | L2 Procurement Lead |
| Any mandatory L3 trigger (§2) | L3 Human Owner |

## 4. Escalation Record (required)

Every escalation is recorded — never a verbal/lost hand-off. Minimum fields:

```markdown
- Escalation: <issue>            Level: L0→L1 / L1→L2 / L2→L3
- Raised by: <role>             To: <head / Lead / Human Owner>
- Class: D0–D4                  Why escalated: <trigger>
- Options / recommendation: <...>   Sources: <links>
- Decision: <filled by resolver>    Decided by / date: <...>
```

Filed in the owning record (`/projects`, `/rfq`, `/cost_down`, `/contracts`) and
referenced from `/memory/current-context.md` while open.

## 5. De-escalation & Closure

- The level that resolves an issue **records the decision and rationale**, then
  returns ownership to the originating role/department.
- A resolved issue is closed in the record; an open issue stays flagged in
  `/memory/current-context.md` with its level and next action.

## 6. Timeliness (guidance)

This is a file-based, asynchronous organization, so escalation is event-driven,
not clock-driven. Guidance: escalate **as soon as** a trigger is met — do not sit
on a blocked item or a commitment-class decision. Hard response SLAs, if KRDA
wants them, are recorded in [`/schedule`](../../schedule/README.md) — marked `TBD`.

## 7. Safety Rule

When in doubt about whether something is a commitment or an exception, **treat it
as one and escalate to L3**. It is always safe to ask the Human Owner; it is never
safe to commit KRDA without authorization.
