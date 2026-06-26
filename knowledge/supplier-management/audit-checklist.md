---
id: supplier-audit-checklist
title: Supplier Audit Checklist
owner: Supplier Development (SM)
status: active
updated: 2026-06-26
links: [../../workflows/supplier_audit.md, ../../skills/supplier_audit.md, ../../templates/audit-report.md, ../../brain/supplier-risk-framework.md]
---

# Supplier Audit Checklist

> Standard capability & quality-system audit for qualifying a supplier. Used by the
> [supplier_audit workflow](../../workflows/supplier_audit.md) and [skill](../../skills/supplier_audit.md);
> findings recorded in the [audit-report template](../../templates/audit-report.md).
> Score each item; only **verified** findings are recorded.

## Scoring

Each section scored 0–5 (0 = absent, 3 = adequate, 5 = strong). Compute a weighted
total; apply gates. **Critical gate items** failing → conditional/fail regardless of total.

| Result | Rule |
|--------|------|
| Qualified | No critical fail; total ≥ 70%; no open major nonconformity |
| Conditional | Minor gaps with CAPA; re-audit on schedule |
| Fail | Any critical gate fail, or total < 50% |

## 1. Company & Legal (weight 10%)
- [ ] Legal registration (DBD), business scope matches supply
- [ ] Tax ID / VAT registration valid
- [ ] Years in business, ownership stability
- [ ] References / existing customers in similar industry

## 2. Quality System (weight 25%) — **critical gate**
- [ ] ISO 9001 (or equivalent) certified & current — *gate*
- [ ] Documented procedures, work instructions in use
- [ ] Incoming / in-process / final inspection defined
- [ ] Calibration program for measuring equipment
- [ ] Nonconformance & CAPA process active
- [ ] Traceability (material certs, lot control)

## 3. Manufacturing Capability (weight 25%) — **critical gate**
- [ ] Processes match the parts to be supplied — *gate*
- [ ] Equipment list, condition, maintenance program
- [ ] Process capability (Cpk) data for key characteristics
- [ ] Tooling design/maintenance capability
- [ ] First-article / PPAP capability

## 4. Capacity & Delivery (weight 15%)
- [ ] Capacity headroom vs KRDA demand
- [ ] Lead-time performance & OTD history
- [ ] Production planning / scheduling system
- [ ] Logistics & packaging adequacy

## 5. Financial & Continuity (weight 10%)
- [ ] Financial stability (no distress signals)
- [ ] KRDA dependency not excessive (single-customer risk)
- [ ] Business continuity / disaster plan

## 6. Sub-tier & Materials (weight 10%)
- [ ] Sub-supplier control (their suppliers qualified)
- [ ] Material sourcing traceable, spec-compliant
- [ ] No conflict/compliance issues (RoHS/REACH where relevant)

## 7. EHS & Ethics (weight 5%)
- [ ] Safe working environment, legal labor practices
- [ ] No child/forced labor; environmental compliance
- [ ] Anti-corruption / ethics acceptable

## Output
- Severity-rate each finding (major / minor / observation) with evidence.
- Set CAPA (owner + due) for each nonconformity.
- Feed score & status to [supplier-risk-framework](../../brain/supplier-risk-framework.md)
  and the supplier scorecard; update `/suppliers/<slug>/`.

## To Tailor for KRDA (`TBD`)
- [ ] Confirm KRDA's required certifications per commodity
- [ ] Confirm Cpk thresholds for critical characteristics
- [ ] Align weights/gates with KRDA quality policy
