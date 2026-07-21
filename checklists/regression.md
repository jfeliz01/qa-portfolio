# Regression Checklist — Swag Labs

**Purpose:** Full regression before a production release.  
**Estimated time:** ~30 minutes  
**Accounts needed:** `standard_user`, `locked_out_user`, `problem_user`, `performance_glitch_user`  
**Updated:** 2026-07-01

---

## Authentication

| # | Check | Pass | Fail | Notes |
|---|---|---|---|---|
| 1 | Login page loads correctly | ☐ | ☐ | |
| 2 | `standard_user` logs in successfully | ☐ | ☐ | |
| 3 | `locked_out_user` receives locked-out error | ☐ | ☐ | |
| 4 | Empty username shows validation error | ☐ | ☐ | |
| 5 | Empty password shows validation error | ☐ | ☐ | |
| 6 | Wrong password shows credential mismatch error | ☐ | ☐ | |
| 7 | Logout clears session and redirects to login | ☐ | ☐ | |
| 8 | Direct access to `/inventory.html` without session redirects to login | ☐ | ☐ | |

---

## Product Catalog

| # | Check | Pass | Fail | Notes |
|---|---|---|---|---|
| 9 | All 6 products display with name, image, price, and button | ☐ | ☐ | |
| 10 | Sort: Name (A to Z) — "Sauce Labs Backpack" first | ☐ | ☐ | |
| 11 | Sort: Name (Z to A) — "Test.allTheThings() T-Shirt" first | ☐ | ☐ | |
| 12 | Sort: Price (low to high) — $7.99 item first | ☐ | ☐ | |
| 13 | Sort: Price (high to low) — $49.99 item first | ☐ | ☐ | |
| 14 | "Add to cart" changes button label to "Remove" | ☐ | ☐ | |
| 15 | "Remove" from catalog decrements cart badge | ☐ | ☐ | |
| 16 | Product detail page loads on name click | ☐ | ☐ | |

---

## Shopping Cart

| # | Check | Pass | Fail | Notes |
|---|---|---|---|---|
| 17 | Cart badge shows correct item count | ☐ | ☐ | |
| 18 | Cart persists items across page navigation | ☐ | ☐ | |
| 19 | Cart page shows name, description, quantity, price | ☐ | ☐ | |
| 20 | Remove item from cart updates badge | ☐ | ☐ | |
| 21 | Empty cart shows no items | ☐ | ☐ | |
| 22 | "Continue Shopping" returns to inventory with cart intact | ☐ | ☐ | |

---

## Checkout

| # | Check | Pass | Fail | Notes |
|---|---|---|---|---|
| 23 | "Checkout" button navigates to Step 1 | ☐ | ☐ | |
| 24 | Empty First Name blocks form submission | ☐ | ☐ | |
| 25 | Empty Last Name blocks form submission | ☐ | ☐ | |
| 26 | Empty Zip Code blocks form submission | ☐ | ☐ | |
| 27 | Valid data on Step 1 proceeds to Step 2 | ☐ | ☐ | |
| 28 | Step 2 shows item subtotal, tax, and total correctly | ☐ | ☐ | |
| 29 | "Finish" completes order and shows confirmation | ☐ | ☐ | |
| 30 | Cart badge clears after order completion | ☐ | ☐ | |
| 31 | "Cancel" on Step 1 returns to cart | ☐ | ☐ | |
| 32 | "Back" on Step 2 returns to Step 1 | ☐ | ☐ | |

---

## Known Issues (do not flag as new failures)

| Known Issue ID | Description |
|---|---|
| KI-001 | `problem_user`: all product images show incorrect dog image |
| KI-002 | `problem_user`: sort filter has no effect on inventory |
| KI-003 | `performance_glitch_user`: no loading indicator during login |

---

**Total checks:** 32  
**Pass:** ___ / 32  
**Fail:** ___  
**Blocked:** ___

**Overall result:** ☐ Pass &nbsp;&nbsp;&nbsp; ☐ Fail &nbsp;&nbsp;&nbsp; ☐ Blocked  
**Executed by:** _______________  
**Date:** _______________  
**Build / version:** _______________
