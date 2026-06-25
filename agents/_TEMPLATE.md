---
id: <agent-id>
title: <Employee / Role Name>
type: agent-employee
department: <OPL | SE | SM | CC | TS | IP>
status: draft
updated: YYYY-MM-DD
---

# <Employee / Role Name>

> One-line identity statement.

## 1. Purpose
Why this employee exists.

## 2. Responsibilities
- ...

## 3. Inputs

| Input | Source |
|-------|--------|
| ... | `/...` |

## 4. Outputs

| Output | Destination |
|--------|-------------|
| ... | `/...` |

## 5. Decision Authority
Per [Decision Framework](../company/decision-framework.md) (D0–D4).

| May decide alone | Must recommend / escalate |
|------------------|---------------------------|
| ... (D0/D2 in-charter) | ... (D3/D4 → Human Owner) |

## 6. Escalation Path
Per [Escalation Rules](../company/organization/escalation-rules.md) (L0–L3).

`L0 self → L1 <dept head> → L2 Procurement Lead → L3 Human Owner`
- Escalate when: ...

## 7. Daily Routine
Recurring attention (rhythm, not a workflow).
- [ ] ...

## 8. Weekly Routine
- [ ] ...

## 9. KPI
Tracked indicators (definitions in `/knowledge/taxonomy`).

| KPI | Target |
|-----|--------|
| ... | TBD |

## 10. Communication Protocol
Per [Communication Rules](../company/organization/communication-rules.md).
- Hand-off in/out: ...
- Confidentiality: ...

## 11. Knowledge Scope
Authoritative knowledge this employee reads/owns, and the brain frameworks it must use.

- Reads: `../knowledge/...`
- Contributes to: `../knowledge/...`
- **Frameworks (mandatory):** `../brain/...` — this employee reasons through these.

## 12. Expected Reasoning Style
How this employee should think.
- ...

## 13. Limitations
What this employee must NOT do / known constraints.
- ...

## 14. Success Metrics
What "doing this job well" looks like (outcomes).
- ...

## 15. Examples
Worked examples / reference cases (link [/simulation](../simulation/README.md) scenarios).
- ...

## 16. Common Mistakes
Recurring errors this role must avoid.
- ❌ ...

## 17. Training Materials
What this employee studies to do the job (knowledge articles, frameworks, scenarios).
- Knowledge: `../knowledge/...`
- Frameworks: `../brain/...`
- Scenarios: `../simulation/...`

## 18. Continuous Learning Plan
How this role improves over time.
- Reviews `lessons_learned` for its domain each week.
- Updates owned knowledge when a gap is found ([/improvement](../improvement/README.md)).
- Practices on new simulation scenarios; tracks AI-accuracy KPI.
