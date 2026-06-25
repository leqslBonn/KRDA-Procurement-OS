---
id: cmd-<name>
title: /<name>
type: command
trigger: "/<name> <args>"
dispatches_to: [<../workflows/...>]
owner: Chief of Staff
status: draft
updated: YYYY-MM-DD
---

# /<name>

> One-line statement of what invoking this command does.

## Purpose
What the command achieves.

## Invocation

```
/<name> <required-arg> [optional-arg]
```

| Argument | Required | Meaning |
|----------|----------|---------|
| ... | yes/no | ... |

## Preconditions
- ...

## What It Does (dispatch)
1. [Chief of Staff] Validate args; classify (D0–D4).
2. [<employee>] ... → invokes `../workflows/...` / `../skills/...`
3. ...

## Memory Routing
Per [architecture.md](../memory/architecture.md).
- Canonical record: `/...`
- Stable ID: `...`
- Index register row: `../memory/...`

## Outputs

| Output | Destination |
|--------|-------------|
| ... | `/...` |

## Approval Gates
- ... (commitments → Human Owner, D3)

## Example
```
/<name> ...
```

## Links
- Workflow(s): `../workflows/...`
- Skill(s): `../skills/...`
