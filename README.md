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
├── BUG-001-multiple-payment-methods-default.md
├── BUG-002-email-replies-not-syncing.md
├── BUG-003-staff-status-toggle-persistence.md
├── BUG-004-duplicate-phone-validation.md
├── BUG-005-compose-toolbar-hidden.md
└── BUG-006-business-name-invalid-input.md

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

## Bug Reports

6 sanitized real-world bug reports covering a range of QA scenarios commonly found in SaaS applications:

| ID | Title | Severity | Priority |
|---|---|---|---|
| BUG-001 | Multiple payment methods displayed as default after refresh | High | High |
| BUG-002 | Inbound email replies not syncing back to application inbox | High | High |
| BUG-003 | Staff status toggle does not persist correctly across environments | High | High |
| BUG-004 | Duplicate phone number validation fails during staff creation | Medium | High |
| BUG-005 | Compose toolbar options become hidden at specific screen width | Medium | High |
| BUG-006 | Business name field accepts whitespace and HTML-like input | Medium | Medium |

These cover: **data persistence**, **third-party integrations**, **access control**, **responsive UI**, **create vs edit validation gaps**, and **input sanitization**.

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

## Summary

| Artifact | Count |
|---|---|
| Test plans | 1 |
| Test cases | 21 |
| Bug reports | 6 |
| Smoke checks | 8 |
| Regression checks | 32 |

---

## License

MIT © Joel Feliz
