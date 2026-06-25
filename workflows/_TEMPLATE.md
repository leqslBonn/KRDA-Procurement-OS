---
id: <workflow-id>
title: <Workflow Name>
type: workflow
owner: <employee (dept)>
status: draft
updated: YYYY-MM-DD
---

# <Workflow Name>

> One-line purpose.

## Flow (BPMN-like)

Legend (canonical: [README](README.md#bpmn-notation)):
`●` start · `[task — Role]` · `◇Gn` XOR gateway · `⚑` escalate · `⇒` calls workflow · `◉` end

```
● ──► [task — Role] ──► ◇G1 <condition?>
                          ├─ yes ─► [task — Role] ──► ◉
                          └─ no ──► ⚑ escalate / ⇒ other_workflow
```

## 1. Purpose
Why this workflow exists.

## 2. Inputs

| Input | Source |
|-------|--------|
| ... | `/...` |

## 3. Required AI Employees

| Employee | Dept | Role in this flow |
|----------|------|-------------------|
| ... | ... | ... |

## 4. Decision Gates

| Gate | Condition | Yes → | No → |
|------|-----------|-------|------|
| G1 | ... | ... | ... |

## 5. Outputs

| Output | Destination |
|--------|-------------|
| ... | `/...` |

## 6. Escalation Rules
Per [escalation-rules](../company/organization/escalation-rules.md) (L0–L3).

- L1 (dept head): ...
- L2 (Procurement Lead): ...
- L3 (Human Owner / commitment gate): ...

## 7. KPI

| KPI | Target |
|-----|--------|
| ... | TBD |

## 8. Checklist

- [ ] ...

## 9. Common Mistakes

- ❌ ...

## 10. Automation Opportunities

- ⚙ ...
