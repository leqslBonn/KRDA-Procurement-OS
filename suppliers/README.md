# /suppliers

Supplier master records — the **single source of truth** for supplier facts:
identity, capability, qualification status, and performance.

> ทะเบียนผู้ขาย — แหล่งข้อมูลจริงเพียงที่เดียวเรื่องผู้ขาย

## Structure

```
/suppliers
  _TEMPLATE/
    README.md           ← supplier profile
  <supplier-slug>/
    README.md           ← profile (identity, capability, status)
    scorecard.md        ← from templates/supplier-scorecard.md
    audits/             ← audit reports
```

## Conventions

- One folder per supplier, `kebab-case` slug.
- Supplier facts live **here only**; RFQs, projects, and contracts link to them.
- Qualification status is authoritative here: `qualified / conditional /
  disqualified / prospective`.
- Never delete a supplier; archive via status.

## Confidentiality
Supplier identities, capabilities, and especially prices are confidential. Prices
belong with quotes in `/rfq`, not in the supplier profile.
