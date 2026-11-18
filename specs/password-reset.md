# Password reset

**Sent by:** Afiax Clinical Suite server, `packages/server/src/auth/resetpassword.ts`
**Sent to:** someone who chose "Forgot password" on a sign-in page
**Trigger:** `POST /auth/resetpassword`

## Subject and preview line

- Subject: `Reset your Afiax password`
- Preview: `Someone asked to reset the password for {{email}}. The link works once.`

## Must answer

1. **What happened:** someone asked to reset the password for this email address.
2. **Why me:** the request was made on the Afiax sign-in page with this address. Give the
   time (EAT) and, if available, the browser and approximate place.
3. **What now:** 1. Choose a new password (button + plain link). 2. Sign in with it.
4. **Need:** at least 8 characters, not in a known data leak.
5. **Next:** the old password stops working when the new one is set. Other signed-in
   sessions: say what really happens (check before writing).
6. **Not you:** "Your password has not changed. You can ignore this email. If you keep
   getting these, tell Afiax support." Help: Afiax support.

## Details box

Account (email) · Requested at · From (browser, if known)

## Data the app must supply

`email`, `resetUrl`, `requestedAt` (formatted, EAT), `userAgent` summary (optional),
`signInUrl`, `supportEmail`.

## Gaps found in the code

- Same as invite: the link never expires.
- Request time and browser aren't passed to the email today.
- Organisations that sign in through an external identity provider can't reset here
  (`isExternalAuth`). They currently get no email; consider telling them where to reset.
