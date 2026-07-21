# Bug Report: Inbound Email Replies Not Syncing Back to Application Inbox

| Field | Details |
|---|---|
| **ID** | BUG-002 |
| **Severity** | High |
| **Priority** | High |
| **Reported by** | Joel Feliz |
| **Date** | 2026-07-01 |
| **Module** | Inbox > Email Channel |

---

## Summary

Outbound emails are successfully delivered to the recipient, but replies are not syncing back into the application Inbox. Replies are received in the external email provider mailbox instead.

---

## Environment

| Field | Value |
|---|---|
| **Application** | SaaS Inbox / Messaging Module |
| **Module** | Inbox > Email Channel |
| **Environment** | QA / Staging |
| **Providers Tested** | Gmail / Microsoft 365 |
| **Browser** | Chrome |
| **Device** | Desktop |

---

## Preconditions

- User has an email channel connected.
- User can send outbound messages from the application Inbox.
- Recipient can reply to the received email.

---

## Steps to Reproduce

1. Log in to the application.
2. Connect an email channel.
3. Navigate to Inbox.
4. Send an email message to an external recipient.
5. Confirm the recipient receives the email.
6. Reply to the message from the recipient mailbox.
7. Check the application Inbox.
8. Check the connected external mailbox.

---

## Expected Result

The reply should sync back into the application Inbox conversation.

---

## Actual Result

The reply is delivered to the external mailbox but does not appear in the application Inbox.

---

## Impact

Users may miss customer replies inside the application, creating communication gaps and reducing trust in the Inbox integration.

---

## Severity

High

## Priority

High

---

## Notes

Outbound delivery works, but inbound sync does not. This may indicate a provider connection issue, reply-to handling issue, webhook/sync failure, or mismatch between the connected provider and the sending identity.
