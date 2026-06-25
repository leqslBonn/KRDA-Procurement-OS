---
id: decision-framework
title: Decision Framework
owner: Procurement Lead
status: active
updated: 2026-06-25
---

# Decision Framework

How decisions are made, by whom, and where the **commitment gate** sits. Bound by
the [Constitution](constitution.md) (Articles IV–V) and [Core
Principles](core-principles.md).

> กรอบการตัดสินใจ — ใคร ตัดสินอะไรได้ และจุด "commitment gate" ที่ต้องให้คนอนุมัติ

---

## 1. Decision Classes

| Class | Description | Who decides |
|-------|-------------|-------------|
| **D0 — Operational** | Within an agent's charter, no commitment (analysis, drafting, comparison). | Owning agent |
| **D1 — Coordination** | Cross-agent routing, prioritization, sequencing. | Procurement Lead |
| **D2 — Recommendation** | Award rec, sourcing rec, savings case — proposes a commitment. | Owning agent → Lead reviews |
| **D3 — Commitment** | Binds KRDA: spend, award, PO posting, contract term, policy exception. | **Human Owner only** |
| **D4 — Constitutional** | Changes Vision/Mission/Principles/Framework/Constitution. | **Human Owner only** |

**The Commitment Gate sits between D2 and D3.** Agents may take D0–D2 freely
within charter. D3–D4 are reserved to the Human Owner and cannot be bypassed,
automated away, or implied.

## 2. Authority Matrix (RACI)

R = Responsible · A = Accountable · C = Consulted · I = Informed

| Decision | Owning Agent | Procurement Lead | Human Owner |
|----------|:---:|:---:|:---:|
| Operational work (D0) | R/A | I | — |
| Routing / priority (D1) | C | R/A | I |
| Recommendation (D2) | R | A | C |
| Commitment (D3) | R (prepares) | C | **A** |
| Constitutional change (D4) | — | C | **A** |

## 3. Standard Decision Procedure

```
1. Frame      — state the decision, scope, and class (D0–D4).
2. Gather     — pull facts from /knowledge, /suppliers, records (cite sources).
3. Options    — list viable options with trade-offs; no fabricated data.
4. Evaluate   — score against stated criteria (cost, quality, risk, lead time).
5. Recommend  — owning agent proposes; Lead reviews for scope & integrity.
6. Gate       — if D3/D4 → escalate to Human Owner for approval.
7. Record     — write the decision, rationale, and approver to the owning folder.
```

## 4. Decision Criteria (default weighting guidance)

Unless a category strategy says otherwise, evaluate sourcing/award decisions on:

| Criterion | Why it matters |
|-----------|----------------|
| Total cost (TCO, not just unit price) | Real cost to KRDA |
| Quality & capability | Fitness and defect risk |
| Lead time & delivery reliability | Production continuity |
| Supply risk (single-source, geography, capacity) | Continuity & resilience |
| Terms (payment, warranty, flexibility) | Commercial value |

Criteria and weights are recorded in the decision; they are not assumed silently.

## 5. Escalation Triggers (must go to Human Owner)

- Any D3 commitment (spend, award, PO, contract term).
- Any exception to a Core Principle or policy (D4-adjacent).
- Single/sole-source designation.
- Unresolved conflict of interest or supplier dispute.
- Material risk to supply continuity or compliance.

## 6. Conflict Resolution

- **Agent vs. agent (scope/ownership):** Procurement Lead decides routing.
- **Principle vs. principle:** apply the precedence order in
  [Core Principles §Precedence](core-principles.md).
- **Recommendation vs. Human Owner:** Human Owner prevails; rationale recorded.

## 7. Recording a Decision (minimum)

```markdown
- Decision: <what>           Class: D0–D4
- Options considered: <...>  Criteria/weights: <...>
- Chosen: <...>              Rationale: <...>
- Sources: <links>           Approver (if D3/D4): <Human Owner, date>
```
Filed in the owning record (`/projects`, `/rfq`, `/cost_down`, `/contracts`).
