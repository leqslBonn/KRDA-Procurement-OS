# /projects

Active and past procurement initiatives. **One folder per project** — the place
where multi-step work and its records live.

> งานจัดซื้อแต่ละเรื่อง — หนึ่งโฟลเดอร์ต่อหนึ่งโปรเจกต์

## What Counts as a Project

Anything with a start, an objective, and an outcome: a new-part sourcing, a
cost-down campaign, a supplier qualification drive, a category review.

## Structure

```
/projects
  _TEMPLATE/            ← copy this to start a new project
  PRJ-2026-001-<slug>/
    README.md           ← project charter & status
    log.md              ← dated decision/work log
    ...                 ← analyses, drafts, links to /rfq, /cost_down, etc.
```

## Conventions

- Project ID: `PRJ-YYYY-NNN`. Folder: `PRJ-YYYY-NNN-<short-slug>`.
- The project `README.md` carries the document header with `status`.
- Records that have their own home (quotes, contracts, supplier data) live in
  `/rfq`, `/contracts`, `/suppliers` and are **linked** from the project — not copied.
- Close a project by setting `status: archived`; never delete.

## Files

| File | Purpose |
|------|---------|
| [_TEMPLATE/README.md](_TEMPLATE/README.md) | Project charter template. |
