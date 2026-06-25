# /contracts

Contracts, agreements, and binding terms — the record of KRDA's live commitments
with suppliers.

> สัญญาและข้อตกลงผูกพัน — บันทึกข้อผูกพันที่มีผลกับผู้ขาย

## Structure

```
/contracts
  CTR-YYYY-NNN-<supplier-slug>/
    README.md        ← contract summary & key terms (single source)
    documents/       ← signed files / references
```

## Conventions

- Contract ID: `CTR-YYYY-NNN`.
- The `README.md` holds the **authoritative key terms** (parties, scope, pricing
  basis, validity, payment, termination). Other docs link here — never restate terms.
- Link the supplier (`/suppliers`) and any originating RFQ/project.
- **Commitment gate:** contracts represent financial/legal commitment — every
  new or changed term requires human owner approval. Agents prepare; humans sign.
- Never delete; archive expired contracts via status.

## Confidentiality
Contract terms and pricing are strictly confidential.

## Status flow
`draft → under-review → approved → active → expired/archived`
