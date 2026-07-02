# Bug Report: Business Name Field Accepts Invalid Input

| Field | Details |
|---|---|
| **ID** | BUG-006 |
| **Severity** | Medium |
| **Priority** | Medium |
| **Status** | Open |
| **Reported by** | Joel Feliz |
| **Date** | 2026-07-01 |
| **Module** | Settings > Account Profile > Business Information |

---

## Summary

The Business Name field accepts invalid values, including whitespace-only input, excessively long text, and HTML-like tags.

---

## Environment

| Field | Value |
|---|---|
| **Application** | SaaS Account Management Portal |
| **Module** | Settings > Account Profile > Business Information |
| **Environment** | QA / Staging |
| **Browser** | Chrome |
| **Device** | Desktop |

---

## Preconditions

- User is logged in.
- User has permission to edit business information.

---

## Steps to Reproduce

1. Log in to the application.
2. Navigate to Settings.
3. Open Account Profile.
4. Go to Business Information.
5. Edit the Business Name field.
6. Enter whitespace-only text.
7. Save the changes.
8. Repeat the test using HTML-like input such as `<script>alert("test")</script>`.
9. Repeat the test using an excessively long business name.

---

## Expected Result

The field should reject whitespace-only values, enforce a reasonable character limit, and sanitize or block HTML-like input.

---

## Actual Result

The field accepts whitespace-only values, long text, and HTML-like input. The HTML-like input is stored as literal text.

---

## Impact

Invalid business names can affect data quality, display consistency, integrations, reporting, and downstream user-facing areas.

---

## Severity

Medium

## Priority

Medium

---

## Notes

No script execution was observed during testing, but input validation and sanitization should be enforced to protect data quality and reduce future risk.
