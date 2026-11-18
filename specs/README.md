# Email specs

One file per email that our apps send. Each spec says who gets the email, what it must
answer (the six questions in [CONTENT.md](../CONTENT.md)), and what data the app has to
supply. Write or update the spec first, then the template.

| Email | Sent by | Spec | Template | Status |
|---|---|---|---|---|
| Invite (new and existing users) | Afiax Clinical Suite | [invite.md](invite.md) | [emails/invite](../emails/invite.mjml) | **Built** |
| Password reset | Afiax Clinical Suite | [password-reset.md](password-reset.md) | | Spec |
| Email address change | Afiax Clinical Suite | [email-change.md](email-change.md) | | Spec |
| Emergency access (break-glass) alert | Afiax Clinical Suite, Kenya | [break-glass-alert.md](break-glass-alert.md) | | Spec |
| Outbreak alert | Afiax Clinical Suite, Kenya | [outbreak-alert.md](outbreak-alert.md) | | Spec |
| IDSR immediate notification | Afiax Clinical Suite, Kenya | [idsr-immediate.md](idsr-immediate.md) | | Spec |
| Signup confirmation | Oortcloud Console | [signup-confirmation.md](signup-confirmation.md) | | Spec |
| Services ready | Oortcloud Console | [services-ready.md](services-ready.md) | | Spec |
| Billing notices | Oortcloud Console | [billing-notice.md](billing-notice.md) | | Spec |
| Access review due or overdue | Oortcloud Console | [access-review.md](access-review.md) | | Spec |
| Training overdue | Oortcloud Console | [training-overdue.md](training-overdue.md) | | Spec |

Not covered yet: Afiax IAM (Zitadel) sign-in and verification emails, Zulip notifications,
and the built-in Frappe notifications on client Finance, HR and Academy sites.

## Spec template

```markdown
# <Email name>

**Sent by:** app, file and function
**Sent to:** who, and why they get it
**Trigger:** what makes it go out

## Subject and preview line
## Must answer
1. What happened? 2. Why me? 3. What do I do now? 4. What do I need, by when?
5. What happens next? 6. Who can help / what if this wasn't me?
## Details box
## Data the app must supply
## Gaps found in the code
```
