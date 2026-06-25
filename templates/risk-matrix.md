---
id: TPL-RISK-MATRIX
title: Risk Matrix — Template
type: template
status: active
updated: 2026-06-25
---

# Risk Matrix — <Scope (supplier / part / category / project)>

> Score a risk with Likelihood × Impact, then register it. The risk **rows** live in
> [risk_database.md](../memory/risk_database.md) (canonical); this form is the per-risk
> assessment, method from the [supplier_risk skill](../skills/supplier_risk.md).

## Severity Matrix (Likelihood × Impact)

| L \\ I | Low (1) | Med (2) | High (3) |
|--------|---------|---------|----------|
| **High (3)** | 3 | 6 | 9 |
| **Med (2)** | 2 | 4 | 6 |
| **Low (1)** | 1 | 2 | 3 |

Bands: 1–2 low · 3–4 medium · 6–9 high (escalate ≥6 to Human Owner, L3).

## Risk Assessment

| Field | Value |
|-------|-------|
| Risk ID | RSK-YYYY-NNN |
| Type | supply / single-source / quality / compliance / financial / continuity |
| Description | ... |
| Affected (link) | `/suppliers/...` / `/projects/...` / `/contracts/...` |
| Likelihood (1–3) | ... |
| Impact (1–3) | ... |
| **Severity** | L×I |
| Owner | <employee/dept> |
| Mitigation | ... |
| Status | open / mitigating / closed |
| Escalated | L3? (date) |

## Register
Add/update this risk as a row in [risk_database.md](../memory/risk_database.md);
material risks (≥6) are logged in [meeting_history.md](../memory/meeting_history.md).
