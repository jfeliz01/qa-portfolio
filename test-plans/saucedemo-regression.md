# Test Plan — Swag Labs (Saucedemo) Regression Suite

## 1. Overview

| Field | Details |
|---|---|
| **Application** | Swag Labs — [https://www.saucedemo.com](https://www.saucedemo.com) |
| **Type** | Regression |
| **Version** | 1.0 |
| **Author** | Joel Feliz |
| **Date** | 2026-07-01 |

Swag Labs is a demo e-commerce web application built for QA practice. This plan covers the full regression suite for the four core user flows: authentication, product catalog, shopping cart, and checkout.

---

## 2. Scope

### In scope
- Login and logout (valid, invalid, and locked-out scenarios)
- Product catalog (load, sorting, add/remove from catalog)
- Shopping cart (item count, add, remove, navigation)
- Checkout flow (form validation, order completion)
- UI consistency across tested user accounts

### Out of scope
- Performance benchmarking
- Mobile/responsive layout
- Cross-browser compatibility beyond Chrome
- Backend or API layer
- Accessibility audit

---

## 3. Test Environments

| Field | Value |
|---|---|
| **URL** | https://www.saucedemo.com |
| **Browser** | Google Chrome (latest) |
| **OS** | Windows 10 |

### Test accounts

| Username | Password | Purpose |
|---|---|---|
| `standard_user` | `secret_sauce` | Primary happy-path account |
| `locked_out_user` | `secret_sauce` | Validates locked-out error handling |
| `problem_user` | `secret_sauce` | Reveals known defects (images, sort, form) |
| `performance_glitch_user` | `secret_sauce` | Simulates slow network conditions |

---

## 4. Test Types

| Type | Description |
|---|---|
| **Functional** | Verifies expected behavior for valid inputs |
| **Negative** | Verifies system handles invalid input gracefully |
| **Boundary** | Tests edge values (empty fields, single item, max quantity) |
| **Exploratory** | Unscripted sessions to surface unexpected behavior |

---

## 5. Entry Criteria

- Application is accessible at the target URL
- All test accounts are active and passwords confirmed
- Test cases reviewed and approved

## 6. Exit Criteria

- All High and Critical test cases executed
- Zero open Critical bugs
- High severity bugs documented with workaround or accepted risk
- Test execution report generated

---

## 7. Risk Areas

| Area | Risk | Mitigation |
|---|---|---|
| `problem_user` account | Known defects may mask new bugs | Run `standard_user` first; compare results |
| Cart state persistence | Session data may carry over between runs | Clear cookies / use incognito between runs |
| Checkout validation | Client-side only validation may be bypassed | Confirm error messages display before form submits |
| Sort filter | Relies on client-side sorting — no API call | Validate rendered order, not network response |

---

## 8. Test Case Summary

| Module | Total Cases | Functional | Negative | Boundary |
|---|---|---|---|---|
| Login | 6 | 3 | 2 | 1 |
| Inventory | 5 | 3 | 1 | 1 |
| Cart | 4 | 4 | 0 | 0 |
| Checkout | 6 | 2 | 3 | 1 |
| **Total** | **21** | **12** | **6** | **3** |

---

## 9. Deliverables

- Test cases: `test-cases/`
- Bug reports: `bug-reports/`
- Smoke checklist: `checklists/smoke.md`
- Regression checklist: `checklists/regression.md`
