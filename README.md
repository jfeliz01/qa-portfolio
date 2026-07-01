# qa-portfolio

QA documentation portfolio — test plan, test cases, bug reports, and release checklists for [Swag Labs](https://www.saucedemo.com), a public e-commerce demo application built for QA practice.

All artifacts follow professional QA standards: structured test cases with preconditions and expected results, bug reports with reproduction steps and impact analysis, and release checklists with pass/fail tracking.

---

## Contents

```
test-plans/
└── saucedemo-regression.md     # Scope, environments, risk areas, entry/exit criteria

test-cases/
├── login.md                    # 6 cases — valid login, locked user, empty fields, logout
├── inventory.md                # 5 cases — catalog load, sort options, add/remove
├── cart.md                     # 4 cases — item display, badge count, remove, navigation
└── checkout.md                 # 6 cases — full flow, field validation, order summary

bug-reports/
├── BUG-001-broken-product-images.md    # High — wrong images for problem_user
├── BUG-002-sort-filter-no-effect.md    # Medium — sort has no effect for problem_user
└── BUG-003-no-loading-indicator.md     # Low — no feedback during slow login

checklists/
├── smoke.md                    # 8 checks — core flows before regression run
└── regression.md               # 32 checks — full suite before release
```

---

## Application under test

**Swag Labs** — [https://www.saucedemo.com](https://www.saucedemo.com)

A purposely-built demo e-commerce SPA with multiple test user accounts, each exhibiting different behaviors:

| Account | Behavior |
|---|---|
| `standard_user` | Normal happy-path behavior |
| `locked_out_user` | Blocked at login — tests error handling |
| `problem_user` | Broken images, broken sort, broken form — tests defect detection |
| `performance_glitch_user` | Simulated network latency — tests UX under load |

Password for all accounts: `secret_sauce`

---

## Test case format

Each test case includes:
- **ID** — unique identifier (e.g., TC-LOGIN-001)
- **Priority** — Critical / High / Medium / Low
- **Type** — Functional / Negative / Boundary
- **Preconditions** — required state before execution
- **Steps** — numbered, unambiguous
- **Expected Result** — specific, observable outcome

---

## Bug report format

Each bug report includes:
- Severity and priority (separate fields — a Low severity bug can be High priority)
- Environment details (browser, OS, account)
- Steps to reproduce (minimal, verified)
- Expected vs actual result
- Impact analysis
- Notes on root cause hypothesis

---

## Summary

| Artifact | Count |
|---|---|
| Test plans | 1 |
| Test cases | 21 |
| Bug reports | 3 |
| Smoke checks | 8 |
| Regression checks | 32 |

---

## License

MIT © Joel Feliz
