# Invite

**Sent by:** Afiax Clinical Suite server, `packages/server/src/admin/invite.ts`, `sendInviteEmail`
**Sent to:** a person an organisation admin (or the provisioner, or SCIM) adds to an organisation
**Trigger:** `POST /admin/projects/:id/invite` with an email address and `sendEmail` not false

One template covers two cases:
- **New user:** no Afiax account yet. They must create a password.
- **Existing user:** already has an Afiax account. They sign in as usual and choose the new
  organisation.

## Subject and preview line

| Case | Subject | Preview |
|---|---|---|
| New, inviter known | `Jane Wanjiku invited you to Nairobi West Clinic on Afiax` | Set your password to get started. The link works once. |
| New, no inviter | `You're invited to Nairobi West Clinic on Afiax` | same |
| Existing | `You now have access to Nairobi West Clinic on Afiax` | Sign in as usual and choose Nairobi West Clinic. |

## Must answer

1. **What happened:** *Jane* added you to *Nairobi West Clinic* on Afiax.
2. **Why me:** says who added them and why: to work with the team (staff), to see shared
   health information (patient), or about the person they care for (carer).
3. **What now:** new: create password → sign in → set up two-step sign-in (only if
   required). Existing: sign in → choose the organisation.
4. **What they need:** their email address (shown), a password of at least 8 characters
   that isn't in a known leak, and a phone with an authenticator app if two-step sign-in is
   required.
5. **What happens next:** staff see the workspace and their role decides access. Patients
   and carers see what the organisation shares. The password link works once; "Forgot
   password" gets a new one.
6. **Help:** the inviter (with email) for access questions, Afiax support for sign-in
   trouble. "Not expecting this?" note.

## Details box

Organisation · Your role · Invited by (if known) · Your sign-in email · Sign in at

## Data the app must supply

See `emails/invite.json` for the full list. Where each comes from in the server:

| Field | Source |
|---|---|
| `inviterName`, `inviterEmail` | The signed-in user who made the invite request (`ctx.authState.user`). Left out when the request comes from a bot or client application. |
| `roleLabel` | `Administrator` if `membership.admin`; else the access policy's `name`; else Staff member / Patient / Family member or carer by profile type. |
| `setPasswordUrl` | `resetPassword(systemRepo, user, 'invite')` |
| `signInUrl` | `appBaseUrl` + `signin` |
| `mfaRequired` | `request.mfaRequired` |
| `supportEmail` | the address inside `config.supportEmail` |

## Gaps found in the code

- **Set-password links never expire.** `UserSecurityRequest` is single-use, but nothing
  checks its age (`auth/setpassword.ts`). The email therefore says "works once" and gives
  no expiry. Adding an expiry (e.g. 7 days) is a security fix in its own right; when it
  lands, add `expiresAt` to the details box.
- **Staff sign in at `app.`, not `provider.`.** The links use `appBaseUrl`. Clinical staff
  work in the provider app. A `providerBaseUrl` setting (or a per-organisation sign-in URL)
  would send them to the right place.
- **Afiax IAM.** Staff can also use "Sign in with Afiax IAM", but only with an Afiax IAM
  account whose email matches. New invitees usually don't have one, so the email doesn't
  mention it.
- **No help article yet.** `helpUrl` is supported but not set. Add a "Getting started"
  page to the docs site and set it.
