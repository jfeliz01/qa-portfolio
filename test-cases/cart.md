# Test Cases — Shopping Cart

**Module:** Cart  
**URL:** https://www.saucedemo.com/cart.html  
**Updated:** 2026-07-01

---

## TC-CART-001: Cart displays all added items correctly

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Functional |
| **Preconditions** | Logged in as `standard_user`, 2 products added to cart |

**Steps:**
1. Add "Sauce Labs Backpack" and "Sauce Labs Bike Light" to the cart
2. Click the cart icon in the header

**Expected Result:**  
The cart page (`/cart.html`) displays both items, each showing: name, description, quantity (1), and unit price. The cart badge in the header shows **2**.

---

## TC-CART-002: Cart badge reflects the correct item count

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Functional |
| **Preconditions** | Logged in as `standard_user`, cart is empty |

**Steps:**
1. Add "Sauce Labs Bolt T-Shirt" to the cart — observe badge
2. Add "Sauce Labs Onesie" to the cart — observe badge
3. Navigate to another page and return — observe badge

**Expected Result:**  
- After step 1: badge shows **1**
- After step 2: badge shows **2**
- After navigation: badge still shows **2** (cart persists within session)

---

## TC-CART-003: Remove an item from the cart

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Functional |
| **Preconditions** | Logged in as `standard_user`, at least 2 items in cart, on `/cart.html` |

**Steps:**
1. Locate "Sauce Labs Bike Light" in the cart
2. Click its **Remove** button

**Expected Result:**  
- "Sauce Labs Bike Light" is removed from the list immediately
- Cart badge decrements by 1
- Remaining items are unaffected

---

## TC-CART-004: "Continue Shopping" returns to the catalog

| Field | Details |
|---|---|
| **Priority** | Medium |
| **Type** | Functional |
| **Preconditions** | Logged in as `standard_user`, on `/cart.html` |

**Steps:**
1. Click **Continue Shopping**

**Expected Result:**  
User is redirected to `/inventory.html`. Cart contents are preserved — badge still reflects the previously added items.
