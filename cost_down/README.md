# /cost_down

Cost-reduction initiatives and savings tracking. Owned by the **Cost Reduction**
agent. The home for should-cost models, VA/VE ideas, and validated savings.

> กิจกรรมลดต้นทุนและการติดตามผลประหยัด

## Structure

```
/cost_down
  CD-YYYY-NNN-<slug>/
    should-cost.md   ← from templates/should-cost.md
    savings-case.md  ← from templates/savings-case.md
    ideas.md         ← VA/VE idea log
  savings-register.md ← roll-up of all validated savings (single source)
```

## Conventions

- Case ID: `CD-YYYY-NNN`.
- A saving is only counted when **validated against a baseline** and approved.
- The roll-up `savings-register.md` is the single source for total savings;
  individual cases link into it — figures are not duplicated.
- Realized savings link to the SAP record (`sap-purchasing`) and feed
  `/dashboard`.

## Status flow
`idea → in-progress → validated → realized`
