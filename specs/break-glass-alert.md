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

## Gaps found in the code

- Patient name in subject: remove.
- Check that a review screen exists to link to; if not, link to the AuditEvent.
