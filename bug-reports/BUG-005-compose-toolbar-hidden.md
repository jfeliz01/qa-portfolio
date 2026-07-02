# Bug Report: Compose Toolbar Options Become Hidden at Specific Screen Width

| Field | Details |
|---|---|
| **ID** | BUG-005 |
| **Severity** | Medium |
| **Priority** | High |
| **Status** | Open |
| **Reported by** | Joel Feliz |
| **Date** | 2026-07-01 |
| **Module** | Inbox > Compose Message |

---

## Summary

When composing a message at certain desktop widths, key toolbar options become hidden and inaccessible.

---

## Environment

| Field | Value |
|---|---|
| **Application** | SaaS Inbox / Messaging Module |
| **Module** | Inbox > Compose Message |
| **Environment** | QA / Staging |
| **Browser** | Chrome |
| **Resolution** | Approximately 1447px width |
| **Device** | Desktop |

---

## Preconditions

- User is logged in.
- User has access to the Inbox or Leads messaging area.

---

## Steps to Reproduce

1. Log in to the application.
2. Navigate to Inbox.
3. Open an existing conversation or lead.
4. Click Compose.
5. Resize the browser window to approximately 1447px width.
6. Observe the message editor and toolbar area.

---

## Expected Result

All primary actions, including Call, Mark as Complete, and additional menu options, should remain visible or collapse properly into an accessible overflow menu.

---

## Actual Result

The message editor opens automatically and pushes toolbar options out of view. Key actions become hidden and cannot be accessed unless the layout is adjusted.

---

## Impact

Users may be unable to complete important workflow actions from the Inbox, especially on common desktop resolutions. This affects usability and productivity.

---

## Severity

Medium

## Priority

High

---

## Notes

When the text formatting option is not selected, the toolbar collapses more correctly. The issue appears related to responsive layout behavior when the editor is expanded.
