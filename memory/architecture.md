---
id: memory-architecture
title: Memory Architecture
owner: Chief of Staff
status: active
updated: 2026-06-25
---

# Memory Architecture

> The rules that decide — automatically — **where** new information is stored,
> **how** it is indexed, and **how** it is found later. One source of truth, no
> duplication.

This is the design layer above [conventions.md](conventions.md) (read/write rules)
and the registers (the 8 databases). Every employee and the Chief of Staff apply
it whenever information arrives.

---

## 1. Principles

1. **One source of truth.** Each fact has exactly one canonical home.
2. **Never duplicate.** Other places **link**; they never copy.
3. **Classify → Store → Index → Retrieve.** Every intake follows the same path.
4. **Address everything.** Each record gets a stable ID so it can be found later.
5. **Update, don't fork.** If it already exists, update the record — never create a second.

## 2. Memory Layers

| Layer | Holds | Examples |
|-------|-------|----------|
| **Canonical stores** | The truth | `/knowledge`, `/suppliers`, `/company`, `/contracts`, `/projects`, `/rfq`, `/cost_down`; native registers `meeting_history`, `risk_database` |
| **Index registers** | Pointers + light metadata | `supplier_database`, `commodity_database`, `rfq_database`, `cost_database`, `contract_database`, `project_history` |
| **Working state** | "Where we are now" | `current-context.md` |

## 3. The Intake Decision (automatic)

Legend: `●` start · `[task]` · `◇Dn` decision · `◉` end

```
● new information arrives
 └─► [Classify info-type — receiving employee / Chief of Staff]
 └─► ◇D1 <does it already exist? (search by ID + name in the register)>
        ├─ yes ─► [Update the existing canonical record + its register row] ──► ◉
        └─ no ──► [Look up canonical owner in §4 Routing Table]
                    └─► [Write to the canonical store (the one home)]
                    └─► [Add ONE index row in the matching register (link, light metadata)]
                    └─► ◇D2 <is it also a decision or a risk?>
                          ├─ decision/approval ─► [Append to meeting_history.md]
                          ├─ risk ──────────────► [Append to risk_database.md]
                          └─ neither ───────────► continue
                    └─► ◉ stored + indexed + searchable
```

The 4 guaranteed outputs of every intake: **(a)** one canonical record, **(b)**
one index row (if an index register applies), **(c)** a stable ID, **(d)** links
from any place that references it.

## 4. Routing Table (where it goes)

| Info-type arriving | Canonical store (truth) | Index register | Search key |
|--------------------|-------------------------|----------------|-----------|
| Supplier identity / capability / qualification | `/suppliers/<slug>/` | supplier_database | `SUP-<slug>` |
| Commodity / material family | `/knowledge/taxonomy/`, `/standards/` | commodity_database | `CMD-<id>` |
| Spec / drawing / engineering standard | `/knowledge/standards/` (+ project copy) | project_history | drawing/std ref |
| Method / how-to / policy | `/knowledge/<domain>/` | knowledge `index.md` | article id |
| Cost rate / benchmark | `/knowledge/cost/` | cost_database, commodity_database | rate ref |
| Quote / RFQ / award | `/rfq/<id>/` | rfq_database | `RFQ-YYYY-NNN` |
| Should-cost / saving case | `/cost_down/<id>/` | cost_database | `CD-YYYY-NNN` |
| Contract / NDA / terms | `/contracts/<id>/` | contract_database | `CTR-YYYY-NNN` |
| Project / initiative | `/projects/<id>/` | project_history | `PRJ-YYYY-NNN` |
| SAP PR/PO / master-data note | `/projects/<id>/` (+ `/suppliers` note) | rfq_/project_history | PR/PO no. |
| KPI / spend analysis / report | `/dashboard/` (defs in `/knowledge/taxonomy`) | — | report date |
| Decision / approval / review | `meeting_history.md` (native) | — | date + record |
| Risk | `risk_database.md` (native) | — | `RSK-YYYY-NNN` |
| Deadline / recurring task | `/schedule/` | contract_database (expiries) | date |
| Live work state | `memory/current-context.md` | — | — |
| Company / org fact | `/company/` | — | doc id |

> If an item fits two rows, it is **stored once** in the most specific owner and
> **linked** from the other; it is never written twice.

## 5. Addressing & IDs (search keys)

Stable IDs are how memory is found later. Canonical ID definitions live in each
owner folder's README; this is the consolidated addressing map.

| Prefix | Object | Defined in |
|--------|--------|-----------|
| `SUP-<slug>` | Supplier | `/suppliers` |
| `CMD-<id>` | Commodity | `/memory/commodity_database` ↔ `/knowledge/taxonomy` |
| `RFQ-YYYY-NNN` | RFQ | `/rfq` |
| `CD-YYYY-NNN` | Cost-down case | `/cost_down` |
| `CTR-YYYY-NNN` | Contract / NDA | `/contracts` |
| `PRJ-YYYY-NNN` | Project | `/projects` |
| `RSK-YYYY-NNN` | Risk | `/memory/risk_database` |

Rules: IDs are uppercase, never reused, never deleted. Dates `YYYY-MM-DD`.

## 6. Indexing Rules

- A canonical record gets **exactly one** row in **exactly one** index register.
- The index row holds only: ID, name, status, key dates, and the **link** — never
  copied facts, prices, or terms.
- The index row's `status` **mirrors** the canonical record; the record is authoritative.
- Native registers (`meeting_history`, `risk_database`) are append-only and are
  themselves canonical.

## 7. Retrieval (how to find it later)

Four search paths, fastest first:

1. **By ID** — know the key (e.g. `RFQ-2026-014`) → open the canonical record directly.
2. **By register** — scan the matching database table (supplier/rfq/cost/...) →
   follow the link. Filter by status/date/commodity.
3. **By cross-link** — traverse links between registers: supplier ↔ commodity ↔
   risk, rfq ↔ cost, contract ↔ schedule, project ↔ meeting.
4. **By full text** — grep the repo (all Markdown) for a term; entrypoints:
   `/knowledge/index.md` (methods), folder READMEs (records), this file (routing).

Every register lists its links section precisely so retrieval is one hop away.

## 8. Deduplication & One-Source Enforcement

- **Pre-write search is mandatory.** Before creating anything, search the register
  by ID + name. Found → update; not found → create.
- **One home per fact.** A fact written in two files is a defect; collapse to one
  and replace the copy with a link.
- **Periodic audit.** Procurement Automation / Chief of Staff reconcile each
  register against its canonical folder for orphan rows, missing rows, and dupes.

## 9. Conflict Reconciliation

When two sources disagree:

1. Identify the canonical owner via §4; the **owner's record wins**.
2. For numbers, re-task **Procurement Analytics (IP)** to reconcile to source.
3. Correct the wrong copy (or delete it and link the canonical).
4. Log the reconciliation in [meeting_history.md](meeting_history.md).

## 10. Quick Reference (cheat sheet)

```
new info → classify → exists? ── yes → update record + row
                              └─ no  → store in ONE canonical home (§4)
                                       → add ONE index row (link only)
                                       → assign stable ID (§5)
                                       → if decision → meeting_history
                                       → if risk     → risk_database
find later → by ID │ by register │ by cross-link │ by grep
golden rule → link, never copy. one source of truth.
```
