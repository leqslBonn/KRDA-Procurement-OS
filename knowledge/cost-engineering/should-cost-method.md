---
id: should-cost-method
title: Should-Cost Method — Bottom-Up Cost Modeling
owner: Cost Reduction (CC)
status: active
updated: 2026-06-26
links: [material-rates.md, process-rates.md, labor-rates.md, overhead-sga-profit.md, tooling-amortization.md, yield-scrap.md]
---

# Should-Cost Method — Bottom-Up Cost Modeling

> The foundation of all cost-down and negotiation work at KRDA. Build cost from
> first principles; never accept a supplier price without a model.

---

## 1. What Is Should-Cost?

Should-cost = what a part **should** cost if manufactured efficiently, at fair
market rates, with normal profit. It is NOT a supplier's quote — it is the
buyer's independent calculation of fair value.

**Purpose:**
- Set negotiation targets grounded in reality.
- Identify which cost element to attack (material? process? overhead?).
- Detect overpricing without requiring supplier cost disclosure.

---

## 2. The Should-Cost Formula

```
Should-Cost = Material + Process + Labor + Overhead & SGA + Profit + Tooling Amortization
```

Where:

| Element | Source |
|---|---|
| Material | [material-rates.md](material-rates.md) × net weight (+ scrap) |
| Process | [process-rates.md](process-rates.md) × machine time |
| Labor | [labor-rates.md](labor-rates.md) × direct labor hours |
| Overhead & SGA | [overhead-sga-profit.md](overhead-sga-profit.md) × % of (material + process + labor) |
| Profit | [overhead-sga-profit.md](overhead-sga-profit.md) × % of all above |
| Tooling amort. | [tooling-amortization.md](tooling-amortization.md) ÷ lifetime volume |

---

## 3. Step-by-Step Process

### Step 1 — Understand the Part
- Get drawing + material spec + required quantity.
- Identify manufacturing processes (laser cut? weld? machine?).
- Estimate net weight from drawing (or CAD model). Add scrap factor → [yield-scrap.md](yield-scrap.md).

### Step 2 — Calculate Material Cost
```
Material cost = Net weight (kg) × (1 + scrap %) × Material rate (THB/kg)
```
- Rates → [material-rates.md](material-rates.md). Cite rate date.
- If multiple materials, sum each.

### Step 3 — Calculate Process Cost
```
Process cost = Σ (Machine rate THB/hr × Cycle time hr)
```
- Rates → [process-rates.md](process-rates.md).
- Cycle time: estimate from part size, complexity, drawing. Mark as `EST` if not measured.
- Include setup time amortized over batch size.

### Step 4 — Calculate Labor Cost
```
Labor cost = Direct labor hours × Labor rate (THB/hr)
```
- For automated processes, labor hours are low (setup + unload only).
- For manual welding/assembly, labor hours can dominate.
- Rates → [labor-rates.md](labor-rates.md).

### Step 5 — Apply Overhead & SGA
```
Overhead = (Material + Process + Labor) × Overhead % 
SGA = (Material + Process + Labor + Overhead) × SGA %
```
- Typical Thai SME manufacturer: Overhead 15–25%, SGA 5–10%.
- Use supplier-type-appropriate rate → [overhead-sga-profit.md](overhead-sga-profit.md).

### Step 6 — Apply Profit
```
Profit = (all above) × Profit %
```
- Typical Thai supplier: 8–15% net margin.

### Step 7 — Add Tooling Amortization (if applicable)
```
Tooling/unit = Tooling cost ÷ Lifetime volume
```
- Details → [tooling-amortization.md](tooling-amortization.md).
- Only if tooling is supplier-owned and amortized into unit price.

### Step 8 — Sum and Sense-Check
```
Should-Cost = Material + Process + Labor + Overhead + SGA + Profit + Tooling/unit
```
- Compare to market quotes: if quote > should-cost × 1.15 → investigate gap.
- If quote < should-cost × 0.85 → check if supplier is cutting corners or has a real advantage.

---

## 4. Accuracy and Marking

| Situation | Mark |
|---|---|
| Rate from dated source | cite source + date |
| Cycle time measured | cite measurement method |
| Rate estimated / not confirmed | `EST` |
| Weight estimated (no CAD) | `EST` + tolerance |

Never present a should-cost to a supplier as "exact." It is a **buyer's model** — always acknowledge uncertainty while defending the logic.

---

## 5. Output

Use [should-cost template](../../templates/should-cost.md) to record.
Save as `/cost_down/CD-YYYY-NNN/should-cost.md`.
Register in `cost_database.md`.

---

## 6. Common Pitfalls

- Using stale material rates — always check date and refresh if >3 months old.
- Underestimating scrap on complex shapes — use [yield-scrap.md](yield-scrap.md).
- Forgetting setup cost amortization for small batches.
- Applying high-volume process rates to a prototype (100 units) — adjust.
- Claiming the should-cost IS the price — it is a reference, not a demand.
