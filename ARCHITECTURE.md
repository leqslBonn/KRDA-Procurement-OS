# Architecture — KRDA Procurement OS

How the system is organized and how its parts work together. This is the
foundation document; read it with [README.md](README.md) and [CLAUDE.md](CLAUDE.md).

---

## 1. Mental Model

Think of the repository as a **company, not an app**:

- **People** → AI agents in `/agents`, each with a charter.
- **Procedures** → reusable workflows in `/workflows`.
- **Judgment** → decision frameworks in `/brain` (every employee reasons through these).
- **Skills** → reusable analytical methods in `/skills` (invoked by workflow steps).
- **Training** → realistic cases in `/simulation`; learning in `/improvement`.
- **Forms** → standard templates in `/templates`.
- **Company knowledge** → the single source of truth in `/knowledge`.
- **Records / filing cabinet** → `/projects`, `/rfq`, `/cost_down`, `/contracts`,
  `/suppliers`.
- **Front door** → invocable commands in `/commands`.
- **Management view** → `/dashboard` and `/schedule`.
- **Onboarding manual** → `/company`.
- **Working memory** → `/memory`.

Agents are the *actors*; everything else is the *system they operate within*.

---

## 2. Layered Design

```
┌─────────────────────────────────────────────────────────────┐
│  INTERFACE        /commands   /dashboard   /schedule          │  ← entry, views, timing
├─────────────────────────────────────────────────────────────┤
│  ACTORS           /agents                                     │  ← who does the work
├─────────────────────────────────────────────────────────────┤
│  INTELLIGENCE     /brain                                      │  ← how we decide (frameworks)
├─────────────────────────────────────────────────────────────┤
│  PROCESS          /workflows   /skills   /templates           │  ← how work is done
│                   (engine: workflows/ENGINE.md)               │
├─────────────────────────────────────────────────────────────┤
│  RECORDS          /projects /rfq /cost_down /contracts        │  ← what work produced
│                   /suppliers                                  │
├─────────────────────────────────────────────────────────────┤
│  FOUNDATION       /knowledge   /company   /memory             │  ← truth & context
├─────────────────────────────────────────────────────────────┤
│  LEARNING LOOP    /simulation → /memory(lessons) →            │  ← how we get better
│                   /improvement → /brain & /knowledge          │
└─────────────────────────────────────────────────────────────┘
   versioned by  /releases
```

**Dependency direction:** upper layers depend on lower layers, never the reverse.
Actors reason through `/brain` frameworks and read `/knowledge`; neither depends on
actors. The **learning loop** feeds improvements back into `/brain` and `/knowledge`
— the only sanctioned way the foundation changes, keeping it stable yet evolving.

---

## 3. The Agent Team

| Agent | Domain | Primary Output |
|-------|--------|----------------|
| Procurement Lead (Orchestrator) | Routing, coordination, escalation | Task routing, decisions |
| Technical Purchasing | Parts, specs, drawings, qualification | Spec-validated buys |
| Strategic Sourcing | Category strategy, supplier selection | Sourcing plans |
| Supplier Development | Supplier capability, quality, audits | Development plans |
| Cost Reduction | Should-cost, VA/VE, negotiation support | Savings cases |
| RFQ Management | Quote requests, comparison, awards | RFQ packages, bid tabs |
| SAP Purchasing | PO/PR, master data, transactions | SAP-ready records |
| Procurement Analytics | Spend, KPI, reporting | Analyses, dashboards |
| Procurement Automation | Process automation, integration | Workflows, scripts |

Each agent is defined by a charter file in [`/agents`](agents/). See the
[agent registry](agents/index.md).

---

## 4. Knowledge Discipline (No Duplication)

The most important architectural rule:

- A **fact** (a price method, a standard, a supplier's capability) is written
  **once** in its owning folder.
- Other documents **reference** it by relative link.
- When the fact changes, it changes in one place and every reference stays correct.

Owning folders:

- Methods, standards, definitions → `/knowledge`
- Supplier facts → `/suppliers`
- Company facts → `/company`
- Live commitments → `/contracts`

---

## 5. Lifecycle of a Record

```
draft ──► active ──► approved ──► archived
```

Records are never deleted. Status moves forward via the document header
(`status:` field). Archived records stay in place for audit.

---

## 6. Extending the System

To add a capability:

1. **New role?** Add an employee in `/agents` (copy `_TEMPLATE.md`).
2. **New procedure?** Add a workflow in `/workflows` (copy `_TEMPLATE.md`).
3. **New analytical method?** Add a skill in `/skills` (copy `_TEMPLATE.md`).
4. **New document type?** Add a template in `/templates`.
5. **New fact/method?** Add it to `/knowledge` — once.

Never solve a new need by copying an old file's content. Link instead.

---

## 7. Build Status

In place: governance (`/company`), employees (`/agents`), departments
(`/company/organization`), workflows (`/workflows`), skills (`/skills`), templates
(`/templates`), and the memory architecture + registers (`/memory`).

Still to come (added on this stable foundation):

- Real supplier, RFQ, cost, and contract **data**.
- `/knowledge` articles to clear the `TBD` references (rates, standards, KPI defs).
- Live dashboards and automation scripts.
