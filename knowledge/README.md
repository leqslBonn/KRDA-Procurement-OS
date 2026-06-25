# /knowledge — Knowledge System

The **single source of truth** for everything the organization knows: methods,
standards, rates, and references. Organized into domains, searchable, reusable. If
a fact or method is reused anywhere, it is written **here once** and linked.

> คลังความรู้กลาง — แหล่งความจริงเดียว จัดเป็น domain ค้นหาได้ ใช้ซ้ำได้
> เขียนครั้งเดียวที่นี่ แล้ว link ไปใช้ — ห้าม copy

## Domains

| # | Domain | Folder | Primary users |
|---|--------|--------|---------------|
| 1 | Mechanical | [mechanical/](mechanical/) | Technical Purchasing |
| 2 | Electronics | [electronics/](electronics/) | Technical Purchasing |
| 3 | Hydraulics | [hydraulics/](hydraulics/) | Technical Purchasing |
| 4 | Manufacturing | [manufacturing/](manufacturing/) | Tech Purchasing, Cost Reduction |
| 5 | Cost Engineering | [cost-engineering/](cost-engineering/) | Cost Reduction |
| 6 | Supplier Management | [supplier-management/](supplier-management/) | Supplier Development |
| 7 | Strategic Sourcing | [strategic-sourcing/](strategic-sourcing/) | Strategic Sourcing |
| 8 | Negotiation | [negotiation/](negotiation/) | RFQ Mgmt, Cost Reduction |
| 9 | SAP | [sap/](sap/) | SAP Purchasing |
| 10 | Procurement | [procurement/](procurement/) | all |
| 11 | AI Automation | [ai-automation/](ai-automation/) | Procurement Automation |
| 12 | Power Automate | [power-automate/](power-automate/) | Procurement Automation |
| 13 | Excel | [excel/](excel/) | Analytics, Automation |
| 14 | Engineering Standards | [engineering-standards/](engineering-standards/) | Technical Purchasing |

Cross-cutting: [taxonomy/](taxonomy/) (spend categories, KPI definitions).

## How Knowledge Is Used

- **Brain frameworks** cite knowledge for criteria/rates.
- **Skills** read rates/standards (e.g. cost_breakdown → cost-engineering).
- **Workflows** reference knowledge in steps.
- Nobody copies a fact — they **link** to its article.

## Article Standard

- One concept per file, `kebab-case.md`, with a document header.
- Reference data (rates, codes) carries a **source and date**.
- Tag the domain and add a row to [index.md](index.md).

## Searchable & Reusable

Find knowledge four ways (see [memory architecture §7](../memory/architecture.md)):
1. **By index** — [index.md](index.md) lists every article by domain.
2. **By domain** — open the domain folder's README.
3. **By link** — frameworks/skills link directly to the article they use.
4. **By grep** — full-text search across `/knowledge`.

## Files

| File | Purpose |
|------|---------|
| [index.md](index.md) | Master index of all articles (search entrypoint). |
| `<domain>/README.md` | Domain scope, users, and article list. |
