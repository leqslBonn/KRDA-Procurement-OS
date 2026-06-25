---
id: framework-supplier-risk
title: Supplier Risk Framework
type: framework
used_by: [../skills/supplier_risk.md, ../templates/risk-matrix.md]
status: active
updated: 2026-06-25
---

# Supplier Risk Framework

> The dimensions and scoring by which supplier/category risk is rated and acted on.

## Purpose
Make supply risk explicit, comparable, and tracked so continuity is weighed beside cost.

## When to Use
Inside [supplier_risk skill](../skills/supplier_risk.md) and the
[risk-matrix template](../templates/risk-matrix.md).

## Decision Inputs

| Input | Source |
|-------|--------|
| Supplier profile, capability | `/suppliers` |
| Performance (PPM, OTD) | `/suppliers`, `/dashboard` |
| Sourcing structure | [supplier-selection-framework](supplier-selection-framework.md) |

## Framework (criteria & logic)

Risk types scored on Likelihood × Impact (1–3 each → severity 1–9):

| Risk type | Watch for |
|-----------|-----------|
| Single/sole-source | No qualified alternative |
| Supply / capacity | Capacity ceiling, allocation |
| Quality | PPM trend, escapes, weak system |
| Delivery / continuity | OTD trend, geography, disaster exposure |
| Compliance / legal | Cert lapse, regulatory, IP |
| Financial | Instability, dependency on KRDA |

## Decision Rule
- Severity = Likelihood × Impact. Bands: 1–2 low · 3–4 medium · **6–9 high**.
- Each high risk needs an owner + mitigation; sort register by severity.

## Escalation / Commitment Gate
- High risk (≥6) and any single-source → **L3 Human Owner**; logged in
  [risk_database](../memory/risk_database.md) + [meeting_history](../memory/meeting_history.md).

## Pitfalls
- ❌ Treating single-source as routine.
- ❌ Logging a risk with no owner or mitigation.
- ❌ Scoring impact without continuity in mind.

## Links
- Skill: [supplier_risk.md](../skills/supplier_risk.md) · Template: [risk-matrix.md](../templates/risk-matrix.md)
- Register: [risk_database.md](../memory/risk_database.md)
- Knowledge: `../knowledge/supplier-management/`
