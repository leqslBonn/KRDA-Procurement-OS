---
id: project-history
title: Project History (Recall Index)
type: register-index
status: active
updated: 2026-06-25
---

# Project History (Recall Index)

> Timeline and index of all procurement initiatives. **Index only — not the
> source of truth.**

## Source of Truth
Canonical project records live in [`/projects`](../projects/README.md). This file
indexes them for recall — status, dates, outcome, and a link.

## Schema (newest on top)

| Project ID | Title | Owner agent | Status | Started | Closed | Outcome | Record |
|------------|-------|-------------|--------|---------|--------|---------|--------|
| PRJ-2026-001 | DRY-RUN — Machined bracket (pipeline readiness test) | Chief of Staff | active | 2026-06-26 | — | Pipeline OK; gaps logged | [link](../projects/PRJ-2026-001-dryrun-bracket/) |

> 1 project (dry-run / synthetic). Real projects begin v0.12.

## Conventions
- One row per project; `Record` links to `../projects/<id>/`.
- `Status` mirrors the project record header (`draft/active/approved/archived`).
- On close, fill `Closed` and a one-line `Outcome`; never delete the row.

## Links
- Canonical records: [`/projects`](../projects/README.md)
- Decisions within projects: [meeting_history.md](meeting_history.md)
- Related RFQs/cost cases: [rfq_database.md](rfq_database.md), [cost_database.md](cost_database.md)
