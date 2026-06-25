---
id: <skill-id>
title: <Skill Name>
type: skill
owner: <employee (dept)>
used_by: [<workflow.md>, ...]
uses: [<../templates/...>, <../knowledge/...>]
status: draft
updated: YYYY-MM-DD
---

# <Skill Name>

> One-line statement of the capability.

## Purpose
What this skill produces and why.

## When to Use
The workflow step(s) / trigger that invoke this skill.

## Inputs

| Input | Source |
|-------|--------|
| ... | `/...` |

## Method
The actual technique — numbered, reusable, deterministic where possible.

1. ...
2. ...
3. ...

## Output

| Output | Destination / Template |
|--------|------------------------|
| ... | `../templates/...` → `/...` |

## Quality Bar
What "done well" looks like; the checks before hand-off.

- [ ] ...

## Common Errors
- ❌ ...

## Limitations / Guardrails
- ...

## Links
- Workflow(s): `../workflows/...`
- Template(s): `../templates/...`
- Knowledge: `../knowledge/...`
