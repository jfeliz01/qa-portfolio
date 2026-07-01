# BUG-001 — Product images display incorrect content for problem_user

| Field | Details |
|---|---|
| **ID** | BUG-001 |
| **Severity** | High |
| **Priority** | High |
| **Status** | Open |
| **Reported by** | Joel Feliz |
| **Date** | 2026-07-01 |
| **Module** | Product Catalog — Inventory |
| **URL** | https://www.saucedemo.com/inventory.html |

---

## Summary

When logged in as `problem_user`, all product images on the inventory page display the same incorrect image (a dog/pet photo) instead of the actual product images. This makes it impossible to visually identify any product by image.

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

1. Navigate to `https://www.saucedemo.com`
2. Enter username: `problem_user`
3. Enter password: `secret_sauce`
4. Click **LOGIN**
5. Observe the product images on the inventory page

---

## Expected Result

Each product displays its own distinct image:
- Sauce Labs Backpack → backpack image
- Sauce Labs Bike Light → bike light image
- Sauce Labs Bolt T-Shirt → t-shirt image
- *(etc.)*

---

## Actual Result

All 6 product cards display the same image (a photograph of a dog). The `src` attribute on all `<img>` tags points to the same incorrect asset path instead of the individual product image paths.

---

## Impact

- Users cannot visually distinguish products from one another
- High risk of wrong product selection
- Affects the entire product catalog for this user account
- Blocks any visual regression testing for product images

---

## Notes

- Issue is account-specific: does not reproduce with `standard_user`
- Likely caused by a hardcoded or incorrect image `src` in the data layer for `problem_user`
- No console errors observed — the incorrect image loads successfully (not a broken 404)
