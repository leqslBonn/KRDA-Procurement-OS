# /brain — Procurement Brain

The organization's **reusable decision frameworks** — the *criteria and logic* by
which decisions are made. Every AI employee reasons through these frameworks; they
are the shared "how we decide," kept in one place so judgment is consistent and
improvable.

> สมองขององค์กร — กรอบการตัดสินใจที่ใช้ซ้ำได้ (เกณฑ์ + ตรรกะ) ทุก AI employee ต้องใช้

## Where the Brain Sits

```
brain (decision LOGIC / criteria)  ←  the "why & on what basis"
   │  applied by
workflows (PROCESS)  →  skills (METHOD)  →  templates (FORMAT)  →  records
```

- **Framework** = the decision criteria, weights, and rule (canonical here).
- **Workflow** = the process that reaches the decision point.
- **Skill** = the method that computes an input.
- A workflow/skill **invokes** a framework — it never restates the criteria.

This separation means we improve *judgment* in one place (brain) without touching
process (workflows) or format (templates).

## Frameworks

| Framework | Decides | Used by |
|-----------|---------|---------|
| [supplier-selection-framework.md](supplier-selection-framework.md) | Which supplier(s) to shortlist/choose | supplier_selection, Strat Sourcing |
| [supplier-risk-framework.md](supplier-risk-framework.md) | How risky a supplier/category is | supplier_risk, SM/SE |
| [technical-purchasing-framework.md](technical-purchasing-framework.md) | Is a part technically buyable/qualified | technical_review, Tech Purchasing |
| [cost-down-framework.md](cost-down-framework.md) | Which cost lever to pursue | cost_down, Cost Reduction |
| [negotiation-framework.md](negotiation-framework.md) | Negotiation strategy & targets | price_negotiation, RFQ/Cost |
| [make-vs-buy.md](make-vs-buy.md) | Make internally vs buy outside | Strat Sourcing |
| [rfq-evaluation-framework.md](rfq-evaluation-framework.md) | How to score & award quotes | rfq, compare_quotation |
| [engineering-change-framework.md](engineering-change-framework.md) | How to assess & cut in an ECN | engineering_change, Tech Purchasing |
| [delivery-recovery-framework.md](delivery-recovery-framework.md) | How to recover late/short delivery | SM, Procurement Lead |
| [quality-escalation-framework.md](quality-escalation-framework.md) | How to escalate a quality issue | SM, Tech Purchasing |
| [approval-matrix.md](approval-matrix.md) | Who approves what | all (commitment gate) |
| [decision-matrix.md](decision-matrix.md) | Generic weighted multi-criteria decision | all |

## Conventions

- One framework per file; use [_TEMPLATE.md](_TEMPLATE.md).
- A framework states criteria, weights/logic, decision rule, and the escalation gate.
- Frameworks reference [decision-framework](../company/decision-framework.md)
  (D0–D4) and [approval-matrix](approval-matrix.md) — they never bypass the
  Human Owner commitment gate.
- Improve judgment here once; every employee benefits.
