---
id: memory-conventions
title: Memory Conventions
status: active
updated: 2026-06-25
---

# Memory Conventions

Rules for how agents use `/memory` so continuity stays clean and the source of
truth stays in `/knowledge`. For **where new information is routed, indexed, and
retrieved**, follow [architecture.md](architecture.md) — these conventions are the
read/write detail beneath it.

## Write Rules

1. **State, not truth.** Record progress, decisions-in-flight, and next actions —
   not durable facts.
2. **Single live context.** `current-context.md` is the one authoritative "where
   we are now" file. Keep it short and current.
3. **Date everything.** Use `YYYY-MM-DD`. Newest summary on top.
4. **Promote durable facts.** When something becomes a stable fact (a confirmed
   supplier capability, an agreed method), move it to its owning folder and link.

## Read Rules

- At task start, read `current-context.md` first, then only the knowledge needed.
- Never trust memory over a `status: approved` record in the owning folder.

## current-context.md shape (suggested)

```markdown
# Current Context — YYYY-MM-DD

## Active Work
- <project/RFQ id> — <one line status>

## Next Actions
- [ ] ...

## Open Questions / Blocks
- ...
```
