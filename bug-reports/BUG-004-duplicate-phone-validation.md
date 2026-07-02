# Bug Report: Duplicate Phone Number Validation Fails During Staff Creation

| Field | Details |
|---|---|
| **ID** | BUG-004 |
| **Severity** | Medium |
| **Priority** | High |
| **Status** | Open |
| **Reported by** | Joel Feliz |
| **Date** | 2026-07-01 |
| **Module** | Settings > Staff > Create |

---

## Summary

The system prevents duplicate phone numbers when editing an existing staff member, but allows the same duplicate phone number when creating a new staff member.

---

## Environment

| Field | Value |
|---|---|
| **Application** | SaaS Account Management Portal |
| **Module** | Settings > Staff |
| **Environment** | QA / Staging |
| **Browser** | Chrome |
| **Device** | Desktop |

---

## Preconditions

- Admin user is logged in.
- At least one staff member already exists with a saved phone number.

---

## Steps to Reproduce

1. Log in as an admin user.
2. Navigate to Settings.
3. Open Staff.
4. Create a new staff member.
5. Enter a phone number already assigned to another staff member.
6. Complete the remaining required fields.
7. Submit the form.

---

## Expected Result

The system should block the creation of a new staff member using a phone number that is already assigned to another staff profile.

---

## Actual Result

The system allows the new staff member to be created with a duplicate phone number. However, when editing an existing staff member, the same duplicate phone number is correctly blocked.

---

## Impact

Duplicate phone numbers can cause account confusion, routing issues, notification problems, and inconsistent staff records.

---

## Severity

Medium

## Priority

High

---

## Notes

Validation appears to be applied on the edit flow but missing or incomplete on the create flow.
