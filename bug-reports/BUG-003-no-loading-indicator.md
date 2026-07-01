# BUG-003 — No loading indicator during slow login for performance_glitch_user

| Field | Details |
|---|---|
| **ID** | BUG-003 |
| **Severity** | Low |
| **Priority** | Medium |
| **Status** | Open |
| **Reported by** | Joel Feliz |
| **Date** | 2026-07-01 |
| **Module** | Authentication — Login |
| **URL** | https://www.saucedemo.com |

---

## Summary

When logging in as `performance_glitch_user`, the login request takes 5+ seconds to complete due to simulated latency. During this wait, the LOGIN button provides no visual feedback (no spinner, no disabled state, no loading message). The page appears frozen, which may lead users to believe the action failed and attempt to re-click.

---

## Environment

| Field | Value |
|---|---|
| Browser | Chrome 126 |
| OS | Windows 10 |
| Account | `performance_glitch_user` / `secret_sauce` |
| URL | https://www.saucedemo.com |

---

## Steps to Reproduce

1. Navigate to `https://www.saucedemo.com`
2. Enter username: `performance_glitch_user`
3. Enter password: `secret_sauce`
4. Click **LOGIN**
5. Observe the button and page state during the 5-second wait

---

## Expected Result

After clicking LOGIN, the button enters a disabled/loading state (e.g., spinner, "Logging in..." label, or button disabled) and remains so until the response is received. This communicates to the user that the action is in progress.

---

## Actual Result

The LOGIN button remains fully interactive and unchanged throughout the 5+ second wait. No spinner, loading indicator, or state change is shown. The page appears completely static.

---

## Impact

- Users may double-click or re-submit the form, potentially causing duplicate requests
- Creates a poor UX: user cannot tell if the system registered the click
- Low severity because the login ultimately succeeds, but medium priority due to UX risk of repeated submissions

---

## Notes

- The delay is intentional for this account (simulates real-world network latency)
- The missing feedback is a UX defect — not the latency itself
- Recommendation: disable the LOGIN button immediately on click and restore it only on response (success or error)
- Similar patterns in production apps can lead to race conditions if the server processes duplicate submissions
