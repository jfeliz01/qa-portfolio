# Test Cases — Login

**Module:** Authentication  
**URL:** https://www.saucedemo.com  
**Updated:** 2026-07-01

---

## TC-LOGIN-001: Successful login with valid credentials

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Functional |
| **Preconditions** | Browser open, app URL loaded, no active session |

**Steps:**
1. Navigate to `https://www.saucedemo.com`
2. Enter username: `standard_user`
3. Enter password: `secret_sauce`
4. Click **LOGIN**

**Expected Result:**  
User is redirected to `/inventory.html`. The product catalog page displays with the header "Products" and at least one product visible.

---

## TC-LOGIN-002: Login with a locked-out user

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Negative |
| **Preconditions** | Browser open, app URL loaded |

**Steps:**
1. Navigate to `https://www.saucedemo.com`
2. Enter username: `locked_out_user`
3. Enter password: `secret_sauce`
4. Click **LOGIN**

**Expected Result:**  
Login is rejected. Error message displays: *"Epic sadface: Sorry, this user has been locked out."* User remains on the login page.

---

## TC-LOGIN-003: Login with empty username field

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Negative |
| **Preconditions** | Browser open, app URL loaded |

**Steps:**
1. Navigate to `https://www.saucedemo.com`
2. Leave username field empty
3. Enter password: `secret_sauce`
4. Click **LOGIN**

**Expected Result:**  
Login is blocked. Error message displays: *"Epic sadface: Username is required"*. Username field is highlighted with an error indicator.

---

## TC-LOGIN-004: Login with empty password field

| Field | Details |
|---|---|
| **Priority** | High |
| **Type** | Negative |
| **Preconditions** | Browser open, app URL loaded |

**Steps:**
1. Navigate to `https://www.saucedemo.com`
2. Enter username: `standard_user`
3. Leave password field empty
4. Click **LOGIN**

**Expected Result:**  
Login is blocked. Error message displays: *"Epic sadface: Password is required"*. Password field is highlighted with an error indicator.

---

## TC-LOGIN-005: Login with incorrect credentials

| Field | Details |
|---|---|
| **Priority** | Medium |
| **Type** | Negative |
| **Preconditions** | Browser open, app URL loaded |

**Steps:**
1. Navigate to `https://www.saucedemo.com`
2. Enter username: `standard_user`
3. Enter password: `wrongpassword`
4. Click **LOGIN**

**Expected Result:**  
Login is rejected. Error message displays: *"Epic sadface: Username and password do not match any user in this service."* User remains on the login page. No session is created.

---

## TC-LOGIN-006: Logout redirects to login page

| Field | Details |
|---|---|
| **Priority** | Medium |
| **Type** | Functional |
| **Preconditions** | User is logged in as `standard_user` on `/inventory.html` |

**Steps:**
1. Click the hamburger menu (☰) in the top-left corner
2. Click **Logout**

**Expected Result:**  
User is redirected to `https://www.saucedemo.com` (login page). Session is cleared — navigating directly to `/inventory.html` redirects back to login.
