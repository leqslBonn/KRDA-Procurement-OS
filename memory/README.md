# /memory

How the procurement OS **remembers**. This folder holds working state, continuity,
and the **recall registers** the organization queries — without becoming a second
source of truth.

> หน่วยความจำของระบบ — สถานะงานปัจจุบัน + register สำหรับ recall ไม่ใช่คลังความรู้ถาวร

## Three kinds of memory here

| Kind | Files | Source of truth? |
|------|-------|------------------|
| **Working state** | `current-context.md` | Yes (live state only) |
| **Index registers** | `supplier_database`, `commodity_database`, `project_history`, `rfq_database`, `cost_database`, `contract_database` | **No** — they index canonical records elsewhere |
| **Native registers** | `meeting_history`, `risk_database` | **Yes** — no other folder owns this |

## Memory vs. Knowledge (important)

| `/memory` | `/knowledge` |
|-----------|--------------|
| Mutable working state + recall registers | Stable source of truth (methods, facts) |
| "Where are we now / where is it filed" | "What is true / how we do it" |
| Updated often | Updated deliberately |

**Single-source rule still holds.** Index registers store only lightweight
metadata (id, status, dates) and **link** to the canonical record — they never
copy supplier facts, prices, or terms. Native registers (meeting log, risk
register) are canonical *because nothing else owns them*.

**How new information is routed** — where to store it, how to index it, how to
find it later, and how duplication is prevented — is defined in
[architecture.md](architecture.md). Apply it on every intake.

## Files

| File | Type | Indexes / owns |
|------|------|----------------|
| [architecture.md](architecture.md) | design | auto-routing: store / index / retrieve, dedup, one-source |
| [engine.md](engine.md) | design | Memory Engine — auto-update registers on completion |
| [conventions.md](conventions.md) | rules | how agents read/write memory |
| `current-context.md` | state | live handoff state (create when work starts) |
| [supplier_database.md](supplier_database.md) | index | → `/suppliers` |
| [commodity_database.md](commodity_database.md) | index | → `/knowledge`, `/suppliers` |
| [rfq_database.md](rfq_database.md) | index | → `/rfq` |
| [cost_database.md](cost_database.md) | index | → `/cost_down`, `/knowledge/cost` |
| [contract_database.md](contract_database.md) | index | → `/contracts` (+ `/schedule` expiries) |
| [project_history.md](project_history.md) | index | → `/projects` |
| [meeting_history.md](meeting_history.md) | native | decision/meeting log (canonical) |
| [risk_database.md](risk_database.md) | native | risk register (canonical) |
| [negotiation_history.md](negotiation_history.md) | native | negotiation outcomes (canonical) |
| [lessons_learned.md](lessons_learned.md) | native | institutional learning (canonical) |

## Conventions

- One `current-context.md` as the live handoff state.
- Index registers: one row per record; mirror status, link the record, never copy facts.
- Native registers: append-only; correct by adding; never delete history.
- Confidential data (prices, terms, quotes) stays in the owning record, not in registers.
- Always date entries `YYYY-MM-DD`.
