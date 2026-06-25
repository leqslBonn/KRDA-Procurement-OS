---
id: communication-rules
title: Communication Rules
owner: Procurement Lead
status: active
updated: 2026-06-25
---

# Communication Rules

How agents and departments communicate. This organization communicates through
**files, not chat** — every meaningful message is a durable, traceable record.
Bound by the [Constitution](../constitution.md) (Articles VI–VIII) and
[Core Principles](../core-principles.md).

> กฎการสื่อสาร — สื่อสารผ่าน "ไฟล์" ไม่ใช่แชต ทุกข้อความสำคัญเป็น record ที่ตรวจย้อนได้

---

## 1. Communication Channels (where messages live)

| Channel | Medium | Use for |
|---------|--------|---------|
| **Hand-off note** | A note in the owning record (`/projects`, `/rfq`, ...) | Passing work between roles/departments. |
| **Decision / log entry** | Record `log.md` or decision block | Recording a decision, rationale, approval. |
| **Escalation note** | Owning record + flag in `/memory` | Raising an issue up a level (see escalation-rules). |
| **Working state** | `/memory/current-context.md` | "Where we are now"; open items and next actions. |
| **Broadcast / reporting** | `/dashboard` | Status, KPIs, organization-wide updates. |
| **Time-triggered** | `/schedule` | Recurring tasks and deadlines. |
| **Shared truth** | `/knowledge`, `/suppliers`, `/company` | Facts everyone references. |

There is no "private message." Communication is a record in the right channel.

## 2. Standard Message Format (hand-off / request)

Use this block wherever one role asks another to act:

```markdown
### Hand-off — <YYYY-MM-DD>
- From: <role / department>
- To: <role / department>
- Ref: <record id, e.g. RFQ-2026-001 / PRJ-2026-003>
- Class: D0–D4
- Ask: <one sentence — what is needed>
- Context / sources: <links — link, don't copy>
- Due / priority: <date or TBD>
- Status: open
```

When acted on, the receiver appends an outcome and sets `Status: done`, leaving the
full thread intact in the record.

## 3. Routing Rules

1. **Within a department:** members communicate directly; the head is kept informed.
2. **Across departments:** communicate directly per the
   [hand-off map](reporting-lines.md); inform the Procurement Lead. Involve the
   Lead to *decide* only on unclear ownership or conflict.
3. **To the Human Owner:** only through the Procurement Lead (OPL), only for D3/D4.
4. **No silent action:** if a message changes who owns a record, say so explicitly.

## 4. Content Rules

- **Link, don't copy.** Reference the single source of truth; never paste a fact
  that lives elsewhere.
- **Cite sources.** Numbers carry a link/date; unknowns are `TBD`, not guesses.
- **One ask per hand-off.** Keep messages small and actionable.
- **State the decision class** (D0–D4) so the receiver knows the authority needed.
- **Plain, exact language.** Technical terms precise; no ambiguity on commitments.

## 5. Confidentiality in Communication

- **Quotes are sealed:** never disclose one supplier's price/terms to another, and
  never place a supplier's quote where a competing supplier could see it.
- **Prices live with quotes** (`/rfq`) and **terms with contracts** (`/contracts`),
  not in supplier profiles or broadcasts.
- Treat supplier identities, capabilities, and contract terms as confidential by
  default.

## 6. Records Discipline

- Every meaningful message is a file in its channel; conversation is **not** a record.
- Messages are **append-only**: correct by adding, do not erase history.
- Archive closed threads with the record (`status: archived`); never delete.

## 7. Language

- Repository messages and records: **English** for structure, IDs, and tables.
- Explanatory notes may be **bilingual (EN/TH)**; keep technical terms exact.

## 8. Communication Don'ts

- ❌ Decisions or commitments living only in chat.
- ❌ Copying facts between files instead of linking.
- ❌ Cross-supplier disclosure of quotes or terms.
- ❌ Acting on a hand-off whose class is D3/D4 without Human Owner approval.
- ❌ Silent ownership changes.
