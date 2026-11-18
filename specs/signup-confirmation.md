# Signup confirmation

**Sent by:** Oortcloud Console, `oortcloud_console/signup.py`, `send_confirmation`
**Sent to:** the admin email given on the signup form
**Trigger:** someone submits the signup form at `account.`

Since console 0.12.0 this is the only signup email: the Afiax IAM setup link is shown on the
confirmation page, not sent as a separate invitation (ADR-015 §11).

## Subject and preview line

- Subject: `Confirm your email to start your Oortcloud trial`
- Preview: `One click and {{organisationName}}'s {{trialDays}}-day free trial starts.`

## Must answer

1. **What:** you signed up *organisation* for Oortcloud.
2. **Why me:** this address was entered as the admin email.
3. **Now:** 1. Confirm your email (button + link). 2. Sign in to the console. 3. Add
   your team (optional, link to guide).
4. **Need / by when:** the link works once and expires at *date time EAT* (today:
   `LINK_HOURS` hours, so give the actual time).
5. **Next:** what gets set up and how long it takes (the console is ready at once; Finance
   about 20 minutes later, and a second email says so). The trial ends on *date*; what
   happens then and how to pay (M-Pesa, Pesapal).
6. **Not you:** nothing is created until the link is used. Help: Oortcloud support.

## Details box

Organisation · Admin email · Products chosen · Trial length and end date · Link expires

## Data the app must supply

`adminName`, `organisationName`, `products` (list), `trialDays`, `trialEndsOn`,
`confirmUrl`, `linkExpiresAt`, `supportEmail`, `helpUrl`.

Brand: Oortcloud (needs an `oortcloud` brand partial).
