---
id: tooling-amortization
title: Tooling & NRE Amortization
owner: Cost Reduction (CC)
status: active
updated: 2026-06-26
links: [should-cost-method.md, overhead-sga-profit.md]
---

# Tooling & NRE Amortization

> Non-recurring engineering (NRE) and tooling costs must be separated from unit
> price and amortized correctly. Never mix them — they have different risk profiles.

---

## 1. What Is Tooling / NRE?

One-time costs to enable production of a specific part:

| Type | Examples | Typical owner |
|---|---|---|
| Hard tooling | Die set (stamping/casting), mold, dedicated fixture | Usually supplier-owned |
| Soft tooling | CNC program, jig/fixture (reusable) | Supplier-owned |
| NRE | Engineering time for DFM, qualification, PPAP | Supplier or buyer |
| Test & validation | First-article testing, material cert | Supplier or buyer (KRDA R&D context) |

---

## 2. Amortization Formula

```
Tooling cost per unit = Total tooling cost (THB) ÷ Lifetime volume (units)
```

Where **lifetime volume** = expected total production run of this part.

**Example:**
- Die set cost: 120,000 THB
- Expected lifetime: 50,000 units
- Amortization per unit: 120,000 ÷ 50,000 = **2.40 THB/unit**

---

## 3. Decision: Who Owns the Tooling?

| Scenario | Implication |
|---|---|
| Supplier owns tooling, amortizes into unit price | Unit price includes tooling; confirm expected lifetime volume. If KRDA orders less → supplier under-recovers or prices too high. |
| KRDA pays tooling upfront (NRE payment) | Unit price excludes tooling. KRDA owns the tool → can move to another supplier. |
| Shared cost | Split NRE: KRDA pays % upfront; rest amortized into unit price. Agree on "buyout" price if KRDA wants to re-source. |

> **KRDA R&D context:** For prototype/development phases, tooling ownership is critical — if KRDA pays, KRDA can iterate with a different supplier. Always clarify before paying NRE.

---

## 4. Separating Tooling from Unit Price

When a supplier quotes a combined price:
1. Ask for separate line items: (a) unit price ex-tooling, (b) tooling fee.
2. If supplier refuses, estimate tooling cost from:
   - Die complexity (simple = 50–150k THB; complex = 200–500k THB).
   - CNC programming: 0.5–3 hours × 1,500–3,000 THB/hr.
3. Back-calculate implied unit price = Quote − Tooling/unit.

---

## 5. Typical Tooling Costs (Thailand, EST)

| Tool type | Cost range (THB) | Lifetime (units) | THB/unit (est.) |
|---|---|---|---|
| Simple stamping die | 30,000–80,000 | 50,000–100,000 | 0.30–1.60 |
| Progressive stamping die | 150,000–400,000 | 100,000–500,000 | 0.30–4.00 |
| Aluminium die cast mold | 200,000–600,000 | 50,000–200,000 | 1.00–12.00 |
| Sand cast pattern | 20,000–80,000 | 5,000–20,000 | 1.00–16.00 |
| Welding fixture | 20,000–80,000 | — (reuse) | Amort. over production run |
| CNC program (simple) | 1,500–5,000 | — (reuse) | Negligible at volume |
| CNC program (complex 5-axis) | 10,000–30,000 | — (reuse) | Note if prototype only |

> All `EST`. Confirm from toolmaker quotations.

---

## 6. When to Separate NRE in the PO

- For prototypes: always separate — NRE often exceeds unit price for small quantities.
- For production parts >5,000 units lifetime: amortization per unit is typically small (<5% of unit price); can include in unit price if agreed.
- For strategic parts: KRDA should own the tooling (pay NRE upfront) to preserve supply flexibility.

---

## 7. Tooling Lifecycle Tracking

Record in `/suppliers/<slug>/tooling-register.md`:
- Tool ID, part number, location (at supplier), KRDA or supplier owned, condition, estimated remaining life.
- Review annually; replace before tool failure disrupts supply.
