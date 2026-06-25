---
id: TPL-NDA-REVIEW
title: NDA Review — Template
type: template
status: active
updated: 2026-06-25
---

# NDA Review — <Supplier>

> Capture NDA key terms and the review checklist before a Human Owner signs. Used
> by the [nda.md workflow](../workflows/nda.md); the signed record lives in `/contracts`.

| Field | Value |
|-------|-------|
| Contract ID | CTR-YYYY-NNN |
| Supplier | ... |
| Type | one-way / mutual |
| Purpose of disclosure | ... |
| Information scope | <drawings / specs / volumes / prices> |
| Term / duration | ... |
| Governing law | ... |
| Status | draft → under-review → approved → active |

## Review Checklist

- [ ] Disclosure scope is necessary and narrow.
- [ ] Permitted-use clause matches the purpose.
- [ ] Term/duration adequate; expiry set.
- [ ] Return/destruction of information on expiry.
- [ ] Carve-outs (already-known, independently developed) reasonable.
- [ ] Governing law / jurisdiction acceptable.
- [ ] No conflict with existing NDAs (checked `/contracts`).

## Key Terms Summary
<the authoritative key-terms; full document referenced, not pasted>

## Approval (Commitment Gate)
- **NDA is a legal commitment (D3):** prepared by AI, **signed only by Human Owner.**
- Approver: Human Owner, date: ...
- On signature: record in `/contracts/CTR-YYYY-NNN-<supplier>/`; expiry → `/schedule`.
