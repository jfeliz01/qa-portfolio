# Test Cases — Product Inventory

**Module:** Product Catalog  
**URL:** https://www.saucedemo.com/inventory.html  
**Updated:** 2026-07-01

---

## TC-INV-001: Product catalog loads with all items

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Functional |
| **Preconditions** | Logged in as `standard_user` |

**Steps:**
1. Navigate to `/inventory.html`
2. Observe the product grid

**Expected Result:**  
6 products are displayed, each with: product image, name, description, price, and an "Add to cart" button. The sort dropdown defaults to "Name (A to Z)".

---

## TC-INV-002: Sort products by price — low to high

| Field | Details |
|---|---|
| **Priority** | Medium |
| **Type** | Functional |
| **Preconditions** | Logged in as `standard_user`, on `/inventory.html` |

**Steps:**
1. Click the sort dropdown (default: "Name (A to Z)")
2. Select **Price (low to high)**

**Expected Result:**  
Products reorder so the cheapest item appears first ($7.99 — Sauce Labs Onesie) and the most expensive last ($49.99 — Sauce Labs Fleece Jacket). Order is maintained without page reload.

---

## TC-INV-003: Sort products by name — Z to A

| Field | Details |
|---|---|
| **Priority** | Low |
| **Type** | Functional |
| **Preconditions** | Logged in as `standard_user`, on `/inventory.html` |

**Steps:**
1. Click the sort dropdown
2. Select **Name (Z to A)**

**Expected Result:**  
Products reorder alphabetically in descending order. "Test.allTheThings() T-Shirt (Red)" appears first; "Sauce Labs Backpack" appears last.

---

## TC-INV-004: Add a product to the cart from the catalog

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Functional |
| **Preconditions** | Logged in as `standard_user`, cart is empty |

**Steps:**
1. On `/inventory.html`, locate "Sauce Labs Backpack"
2. Click its **Add to cart** button

**Expected Result:**  
- The button label changes to **Remove**
- The cart icon badge in the header updates to show **1**
- No page reload occurs

---

## TC-INV-005: Remove a product from the catalog view

| Field | Details |
|---|---|
| **Priority** | Medium |
| **Type** | Boundary |
| **Preconditions** | Logged in as `standard_user`, "Sauce Labs Backpack" already added to cart |

**Steps:**
1. On `/inventory.html`, locate "Sauce Labs Backpack"
2. Click its **Remove** button

**Expected Result:**  
- Button label reverts to **Add to cart**
- Cart icon badge decrements by 1 (disappears if count reaches 0)
- No page reload occurs
