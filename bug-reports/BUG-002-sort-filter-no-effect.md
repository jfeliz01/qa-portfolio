# BUG-002 — Sort filter has no effect on inventory for problem_user

| Field | Details |
|---|---|
| **ID** | BUG-002 |
| **Severity** | Medium |
| **Priority** | Medium |
| **Status** | Open |
| **Reported by** | Joel Feliz |
| **Date** | 2026-07-01 |
| **Module** | Product Catalog — Sort |
| **URL** | https://www.saucedemo.com/inventory.html |

---

## Summary

When logged in as `problem_user`, selecting any option from the sort dropdown on the inventory page produces no visible change in product order. Products remain in their original order regardless of the selected sort option.

---

## Environment

| Field | Value |
|---|---|
| Browser | Chrome 126 |
| OS | Windows 10 |
| Account | `problem_user` / `secret_sauce` |
| URL | https://www.saucedemo.com/inventory.html |

---

## Steps to Reproduce

1. Log in as `problem_user`
2. Observe the default product order on `/inventory.html`
3. Click the sort dropdown (shows "Name (A to Z)")
4. Select **Price (low to high)**
5. Observe the product order

---

## Expected Result

Products reorder so the lowest-priced item ($7.99 — Sauce Labs Onesie) appears first and the highest-priced item ($49.99 — Sauce Labs Fleece Jacket) appears last.

---

## Actual Result

Product order does not change after selecting a different sort option. The dropdown visually shows the new selection, but the product list remains in its original order.

---

## Impact

- Users cannot sort products by price or name
- Degrades the shopping experience for this user account
- May affect A/B or account-level testing scenarios that rely on sort functionality

---

## Notes

- Does not reproduce with `standard_user` — sort works correctly
- The dropdown UI updates correctly (shows new option selected), suggesting the event handler or re-render logic is broken, not the dropdown itself
- Tested with all four sort options: all produce no change in order
