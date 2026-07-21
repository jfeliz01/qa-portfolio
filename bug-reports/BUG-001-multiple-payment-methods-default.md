# Bug Report: Multiple Payment Methods Displayed as Default After Refresh

| Field | Details |
|---|---|
| **ID** | BUG-001 |
| **Severity** | High |
| **Priority** | High |
| **Reported by** | Joel Feliz |
| **Date** | 2026-07-01 |
| **Module** | Settings > Account Profile > Payment Methods |

---

## Summary

Multiple payment methods are displayed as the default card after refreshing the page, even after selecting a new default payment method.

---

## Environment

| Field | Value |
|---|---|
| **Application** | SaaS Account Management Portal |
| **Module** | Settings > Account Profile > Payment Methods |
| **Environment** | Production / Staging |
| **Browser** | Chrome |
| **Device** | Desktop |

---

## Preconditions

- User has multiple saved payment methods.
- User has access to edit payment methods.

---

## Steps to Reproduce

1. Log in to the application.
2. Navigate to Settings.
3. Open Account Profile.
4. Go to Payment Methods.
5. Add a new payment method.
6. Set the new card as the default payment method.
7. Save the changes.
8. Refresh the page or log out and log back in.
9. Return to Payment Methods.

---

## Expected Result

Only one payment method should be marked as default, and the newly selected default card should persist after refresh.

---

## Actual Result

Two existing payment methods are displayed as default. In some cases, the newly added card disappears temporarily after refresh and reappears later.

---

## Impact

This can confuse users and create uncertainty about which payment method will be charged. It may also indicate a delay or inconsistency between frontend state and backend data persistence.

---

## Severity

High

## Priority

High

---

## Notes

The behavior appears inconsistent after refresh and may be related to delayed synchronization or stale cached payment data.
