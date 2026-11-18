# Email address change

**Sent by:** Afiax Clinical Suite server,
`packages/server/src/fhir/operations/update-user-email.ts`
**Sent to:** the **new** address (to verify it), and the **old** address (a notice).
Today only the new address gets an email.
**Trigger:** `$update-email` operation

## Two emails

### To the new address: "Confirm your new Afiax email address"

1. **What:** your Afiax sign-in email is changing from `a***@old.com` to this address.
2. **Why me:** someone (name the admin if an admin did it, or "you") changed it.
3. **Now:** 1. Confirm this address (button + link). 2. Sign in with the new address next
   time.
4. **Need:** nothing else. Say whether the link expires (it doesn't today).
5. **Next:** until confirmed, what can and can't they do? (Check `emailVerified` handling
   before writing.)
6. **Not you:** tell your administrator or Afiax support straight away.

### To the old address: "Your Afiax sign-in email was changed"

1. **What:** the sign-in email for your account was changed to `n***@new.com` at *time*.
2. **Why:** by *you / admin name*.
3. **Now:** nothing, if you did this.
6. **Not you:** contact Afiax support **now**; include what to say. This is the main
   protection against account takeover, so the security note is prominent, not small text.

## Data the app must supply

`oldEmailMasked`, `newEmailMasked`, `changedBy` (name, optional), `changedAt`,
`verifyUrl`, `supportEmail`.

## Gaps found in the code

- No notice is sent to the old address. Add it.
- Verification links don't expire.
