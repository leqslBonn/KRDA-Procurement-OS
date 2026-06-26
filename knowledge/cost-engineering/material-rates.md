---
id: material-rates
title: Material Rates Reference
owner: Cost Reduction (CC)
status: active
updated: 2026-06-26
links: [should-cost-method.md, yield-scrap.md]
---

# Material Rates Reference

> Rates for should-cost modeling. **Every rate must carry a source and date.**
> Mark estimates `EST`. Update when market moves >5% or rate is >3 months old.
>
> All rates in **THB** unless noted. Exchange rate ref: TH Customs / BOT.

---

## Rate Table — Last Updated 2026-06-26

| Material | Grade / Spec | Form | Rate (THB/kg) | Source | Date | Notes |
|---|---|---|---|---|---|---|
| Mild steel | SS400 / A36 | Plate ≥3mm | 30 `EST` | Market benchmark | 2026-06 | Range 28–32; implement frame |
| Mild steel | SPHC | Hot-rolled coil | 28 `EST` | Market benchmark | 2026-06 | Range 26–30; stamping |
| Mild steel | SPCC | Cold-rolled sheet | 35 `EST` | Market benchmark | 2026-06 | Range 32–38; covers/guards |
| Carbon steel | S45C | Round bar | 42 `EST` | Market benchmark | 2026-06 | Range 38–46; shaft, pin |
| Carbon steel | S55C | Flat bar / plate | 46 `EST` | Market benchmark | 2026-06 | Range 42–50; blade |
| Alloy steel | SCM440 | Round bar | 80 `EST` | Market benchmark | 2026-06 | Range 70–90; high-stress |
| Stainless | SUS304 | Sheet / plate | 170 `EST` | Market benchmark | 2026-06 | Range 150–190; volatile (Ni) |
| Aluminium | A6061-T6 | Plate / bar | 210 `EST` | Market benchmark | 2026-06 | Range 190–240; LME-linked |
| Aluminium | A5052 | Sheet | 200 `EST` | Market benchmark | 2026-06 | Range 180–220 |
| Natural rubber | NR | Sheet / roll | 100 `EST` | Market benchmark | 2026-06 | Range 80–120; TRA-linked |
| NBR rubber | 70 Shore | Sheet | 220 `EST` | Market benchmark | 2026-06 | Range 180–260 |
| HDPE | GP | Sheet / rod | 85 `EST` | Market benchmark | 2026-06 | Range 70–95 |
| PA66 (Nylon) | — | Rod / tube | 240 `EST` | Market benchmark | 2026-06 | Range 190–280 |

> ⚠️ **All rates above are `EST` indicative market benchmarks (mid-2026), NOT KRDA
> contract prices.** Use for first-pass should-cost only. **Before any negotiation or
> binding decision, replace with a real quote** from NS BlueScope Thailand / SSI /
> local service center, or a supplier cost breakdown — then update Source/Date.

---

## How to Use Rates

1. Obtain net part weight from drawing or CAD (kg).
2. Apply scrap factor → [yield-scrap.md](yield-scrap.md).
3. `Material cost = Net weight × (1 + scrap%) × Rate (THB/kg)`
4. If part uses multiple materials, calculate each separately and sum.

---

## Rate Sources (Thailand)

| Material type | Suggested source |
|---|---|
| Steel | NS BlueScope Thailand price list; SSI (Sahaviriya Steel); local service center quotation |
| Aluminium | Thai Aluminium Co. / distributor quotation |
| Rubber | Thai Rubber Association (TRA) natural rubber price; NR price board |
| Plastics | Distributor quotation (LG Chem, SABIC agents in Thailand) |
| International reference | LME (London Metal Exchange) for copper, aluminium, nickel |

---

## Exchange Rate (for import materials)

| Currency pair | Rate | Date | Source |
|---|---|---|---|
| USD/THB | 34.5 `EST` | 2026-06 | BOT (indicative — confirm daily) |
| JPY/THB | 0.235 `EST` | 2026-06 | BOT (indicative) |
| EUR/THB | 37.5 `EST` | 2026-06 | BOT (indicative) |

Import duty rates (Thai Customs) vary by HS code — confirm before using for import materials.

---

## Update Protocol

- Refresh rates when: market news reports >5% steel price movement, or rate date >3 months.
- New rate entry: fill all columns including source URL/document and date.
- Old rate: do not delete — add a new row with new date; keeps history.
