# Emergency access (break-glass) alert

**Sent by:** Afiax Clinical Suite server, `packages/server/src/country-pack/kenya/break-glass.ts`
**Sent to:** the organisation's security and privacy contacts
**Trigger:** a user uses emergency ("break-glass") access to a patient record

## Subject and preview line

- Subject: `Security alert: emergency access used at {{facilityName}}`
- Preview: `{{userName}} opened a patient record with emergency access. Review within 24 hours.`

**Never put the patient's name or ID in the subject or body.** Today's subject does
(`… — ${patientDisplay} — …`). This must change.

## Must answer

1. **What:** *user* used emergency access to open a patient record at *facility*, at *time*.
2. **Why me:** you are listed as a security/privacy reviewer for *organisation*.
3. **Now:** 1. Open the access record in Afiax (button). 2. Check the reason given.
   3. Mark it as justified, or start an investigation.
4. **By when:** the review deadline from the organisation's policy (state it as a date).
5. **Next:** what happens if no one reviews it (escalation, if built).
6. **Help:** Afiax support; the organisation's data protection officer.

## Details box

Organisation · Facility · Used by (name, role) · Time · Reason given · Review by

## Data the app must supply

`facilityName`, `organisationName`, `userName`, `userRole`, `accessedAt`, `reason`,
`reviewBy`, `reviewUrl` (link to the AuditEvent or review screen, behind sign-in).

## Built (2026-11-19)

- The patient's name, ID and the reason are no longer in the subject or body. The reason is
  free text a clinician writes, so it can hold clinical detail; the reviewer reads it in Afiax.
- "Review in Afiax" links to the break-glass Flag in the admin app. Setting the Flag's status
  to Inactive ends the access at once (`security-labels.ts` only honours active flags).
- The review deadline is 24 hours after access starts.

## Gaps

- No dedicated review screen: reviewers use the Flag page in the admin app.
- No escalation if no one reviews it by the deadline.
