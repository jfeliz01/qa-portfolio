# Test Cases — Checkout

**Module:** Checkout Flow  
**URL:** https://www.saucedemo.com/checkout-step-one.html  
**Updated:** 2026-07-01

---

## TC-CHK-001: Complete checkout with valid data

| Field | Details |
|---|---|
| **Priority** | Critical |
| **Type** | Functional |
| **Preconditions** | Logged in as `standard_user`, at least 1 item in cart |

**Steps:**
1. Navigate to `/cart.html`
2. Click **Checkout**
3. Enter First Name: `Joel`
4. Enter Last Name: `Feliz`
5. Enter Zip/Postal Code: `10001`
6. Click **Continue**
7. Review the order summary on Step 2
8. Click **Finish**

**Expected Result:**  
User reaches `/checkout-complete.html`. Page displays: *"Thank you for your order!"* confirmation message. Cart badge is cleared (no items remaining).

---

## TC-CHK-002: Checkout blocked when First Name is empty

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Negative |
| **Preconditions** | Logged in as `standard_user`, at least 1 item in cart, on `/checkout-step-one.html` |

**Steps:**
1. Leave First Name field empty
2. Enter Last Name: `Feliz`
3. Enter Zip/Postal Code: `10001`
4. Click **Continue**

**Expected Result:**  
Form submission is blocked. Error message displays: *"Error: First Name is required"*. User stays on Step 1.

---

## TC-CHK-003: Checkout blocked when Last Name is empty

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Negative |
| **Preconditions** | Logged in as `standard_user`, at least 1 item in cart, on `/checkout-step-one.html` |

**Steps:**
1. Enter First Name: `Joel`
2. Leave Last Name field empty
3. Enter Zip/Postal Code: `10001`
4. Click **Continue**

**Expected Result:**  
Form submission is blocked. Error message displays: *"Error: Last Name is required"*. User stays on Step 1.

---

## TC-CHK-004: Checkout blocked when Zip Code is empty

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Negative |
| **Preconditions** | Logged in as `standard_user`, at least 1 item in cart, on `/checkout-step-one.html` |

**Steps:**
1. Enter First Name: `Joel`
2. Enter Last Name: `Feliz`
3. Leave Zip/Postal Code field empty
4. Click **Continue**

**Expected Result:**  
Form submission is blocked. Error message displays: *"Error: Postal Code is required"*. User stays on Step 1.

---

## TC-CHK-005: Cancel checkout returns to cart

| Field | Details |
|---|---|
| **Priority** | Medium |
| **Type** | Functional |
| **Preconditions** | Logged in as `standard_user`, at least 1 item in cart, on `/checkout-step-one.html` |

**Steps:**
1. Click **Cancel**

**Expected Result:**  
User is redirected to `/cart.html`. All previously added items are still in the cart. No order is created.

---

## TC-CHK-006: Order summary shows correct totals on Step 2

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Boundary |
| **Preconditions** | Logged in as `standard_user`, "Sauce Labs Backpack" ($29.99) in cart, personal info filled |

**Steps:**
1. Complete Step 1 with valid data and click **Continue**
2. On `/checkout-step-two.html`, review the price summary

**Expected Result:**  
- Item total: **$29.99**
- Tax: **$2.40** (8% of item total)
- Total: **$32.39**
- The item name, description, and quantity (1) are displayed correctly
