# Smoke Checklist — Swag Labs

**Purpose:** Verify core functionality is working before a full regression run.  
**Estimated time:** ~5 minutes  
**Account:** `standard_user` / `secret_sauce`  
**Updated:** 2026-07-01

---

Run this checklist after any deployment or environment change. If any item fails, halt regression and escalate.

---

| # | Check | Pass | Fail | Notes |
|---|---|---|---|---|
| 1 | Login page loads at `https://www.saucedemo.com` | ☐ | ☐ | |
| 2 | Login with `standard_user` succeeds and redirects to `/inventory.html` | ☐ | ☐ | |
| 3 | Product catalog displays at least 1 product | ☐ | ☐ | |
| 4 | "Add to cart" button works and badge updates to 1 | ☐ | ☐ | |
| 5 | Cart page (`/cart.html`) shows the added item | ☐ | ☐ | |
| 6 | Checkout Step 1 accepts valid info and proceeds to Step 2 | ☐ | ☐ | |
| 7 | Order completes and confirmation page displays | ☐ | ☐ | |
| 8 | Logout redirects to the login page | ☐ | ☐ | |

---

**Result:** ☐ Pass &nbsp;&nbsp;&nbsp; ☐ Fail  
**Executed by:** _______________  
**Date:** _______________  
**Notes:** _______________
