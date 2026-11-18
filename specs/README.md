# Email specs

One file per email that our apps send. Each spec says who gets the email, what it must
answer (the six questions in [CONTENT.md](../CONTENT.md)), and what data the app has to
supply. Write or update the spec first, then the template.

| Email | Sent by | Spec | Template | Status |
|---|---|---|---|---|
| Invite (new and existing users) | Afiax Clinical Suite | [invite.md](invite.md) | [emails/invite](../emails/invite.mjml) | **Built** |
| Password reset | Afiax Clinical Suite | [password-reset.md](password-reset.md) | [emails/password-reset](../emails/password-reset.mjml) | **Built** |
| Email address change (confirm new + notice to old) | Afiax Clinical Suite | [email-change.md](email-change.md) | [verify](../emails/email-change-verify.mjml), [notice](../emails/email-change-notice.mjml) | **Built** |
| Emergency access (break-glass) alert | Afiax Clinical Suite, Kenya | [break-glass-alert.md](break-glass-alert.md) | [emails/break-glass-alert](../emails/break-glass-alert.mjml) | **Built** |
| Outbreak alert | Afiax Clinical Suite, Kenya | [outbreak-alert.md](outbreak-alert.md) | [emails/outbreak-alert](../emails/outbreak-alert.mjml) | **Built** |
| IDSR immediate notification | Afiax Clinical Suite, Kenya | [idsr-immediate.md](idsr-immediate.md) | [emails/idsr-immediate](../emails/idsr-immediate.mjml) | **Built** |
| Signup confirmation | Oortcloud Console | [signup-confirmation.md](signup-confirmation.md) | [emails/signup-confirmation](../emails/signup-confirmation.mjml) | **Built** |
| Services ready | Oortcloud Console | [services-ready.md](services-ready.md) | [emails/services-ready](../emails/services-ready.mjml) | **Built** |
| Setup needs a hand (provisioning failed) | Oortcloud Console (`provisioning.py` `notify_failed`) | (in the template's .json) | [emails/setup-needs-a-hand](../emails/setup-needs-a-hand.mjml) | **Built** |
| Billing notices | Oortcloud Console | [billing-notice.md](billing-notice.md) | | Spec |
| Access review due or overdue | Oortcloud Console | [access-review.md](access-review.md) | | Spec |
| Training overdue | Oortcloud Console | [training-overdue.md](training-overdue.md) | | Spec |

The console renders the `oortcloud` brand from `dist/python/oortcloud-email-templates.json`
(copied to oortcloud_console/email_templates.json) with the same Mustache subset as Afiax FHIR.

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
