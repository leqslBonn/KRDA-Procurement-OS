---
id: TPL-ACCEPTANCE-CHECKLIST
title: Milestone Acceptance Checklist — Template
type: template
status: active
updated: 2026-06-26
---

# Milestone Acceptance — <Project> / <Milestone>

> Fill per milestone delivery. **Do not release payment until accepted.** "Accepted"
> = meets the SOW acceptance criteria, punch list cleared. The owner's core control point.

| Field | Value |
|-------|-------|
| Project | ... |
| Milestone | M_ (e.g. M3 Integration) |
| Vendor | ... |
| Delivery date | YYYY-MM-DD |
| Acceptance criteria ref | [SOW §4](sow-requirement.md) |
| Payment on accept | __% (+ retention held) |

## 1. Deliverables Received

| Deliverable | Received? | Notes |
|-------------|:---------:|-------|
| Working system / module | ☐ | |
| Source code | ☐ | repo/handover |
| Documentation | ☐ | user + admin + API |
| Data export / handover | ☐ | KRDA-owned format |
| Test results | ☐ | |

## 2. Acceptance Test (against SOW criteria)

| # | Criterion (from SOW) | Test method | Pass? | Evidence |
|---|----------------------|-------------|:-----:|----------|
| A1 | ... | demo / test case / data check | ☐ | |
| A2 | ... | | ☐ | |

## 3. Quality / Security Checks
- [ ] Integration with existing systems works (end-to-end data flow)
- [ ] Security: auth, encryption, hosting/data location acceptable
- [ ] Performance / uptime meets target
- [ ] Usability acceptable for operators/farmers
- [ ] Documentation sufficient to operate without the vendor

## 4. Punch List (defects to fix before sign-off)

| # | Defect / gap | Severity | Vendor fix by | Status |
|---|--------------|----------|---------------|--------|
| 1 | ... | major/minor | YYYY-MM-DD | open |

## 5. Decision

- ☐ **Accepted** — criteria met, punch list cleared → release milestone payment (retention held)
- ☐ **Conditional** — minor punch items; accept with fix deadline
- ☐ **Rejected** — major criteria failed → no payment; vendor reworks

## 6. Sign-off (commitment gate)
- Reviewed by: <you / KRDA owner>
- **Payment release = commitment (D3) → Human Owner approval** per [approval-matrix](../brain/approval-matrix.md).
- Retention released only at final acceptance + warranty end.

> Rule: **pay for accepted work, not promises.** Reject is your strongest lever — use it.
