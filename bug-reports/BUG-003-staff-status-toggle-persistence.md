# Bug Report: Staff Status Toggle Does Not Persist Correctly Across Environments

| Field | Details |
|---|---|
| **ID** | BUG-003 |
| **Severity** | High |
| **Priority** | High |
| **Reported by** | Joel Feliz |
| **Date** | 2026-07-01 |
| **Module** | Settings > Staff |

---

## Summary

The staff status toggle behaves inconsistently across environments. In one environment, a user cannot be reactivated after being deactivated. In another, a user cannot be deactivated after being activated.

---

## Environment

| Field | Value |
|---|---|
| **Application** | SaaS Account Management Portal |
| **Module** | Settings > Staff |
| **Environments** | QA and Production |
| **Browser** | Chrome |
| **Device** | Desktop |

---

## Preconditions

- User has admin access.
- At least one staff member exists.
- Staff status can be updated by toggle.

---

## Steps to Reproduce

1. Log in as an admin user.
2. Navigate to Settings.
3. Open Staff.
4. Select an active staff member.
5. Toggle the staff member to inactive.
6. Save or wait for the change to apply.
7. Refresh the page.
8. Attempt to reactivate the same staff member.
9. Repeat the same flow in another environment if available.

---

## Expected Result

The staff status toggle should consistently allow authorized users to activate and deactivate staff members, and the status should persist after refresh.

---

## Actual Result

The toggle behavior is inconsistent. In one environment, the user cannot be reactivated after deactivation. In another environment, the user cannot be deactivated after activation.

---

## Impact

Admins may be unable to properly manage staff access. This creates access control risk and can block account administration workflows.

---

## Severity

High

## Priority

High

---

## Notes

The issue may be related to environment-specific data state, permission handling, or inconsistent API response handling.
