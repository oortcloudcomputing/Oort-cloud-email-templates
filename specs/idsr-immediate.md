# IDSR immediate notification

**Sent by:** Afiax Clinical Suite server,
`packages/server/src/country-pack/kenya/idsr-delivery.ts`
**Sent to:** the surveillance contacts for an immediately notifiable disease
**Trigger:** a case of an "immediately notifiable" disease is recorded

## Subject and preview line

- Subject: `IDSR immediate: {{diseaseName}} at {{facilityName}}` (today:
  `[IDSR IMMEDIATE] …`: keep the meaning, drop the brackets and capitals).
- Preview: `Notify the sub-county within 24 hours.`

## Must answer

1. **What:** a suspected or confirmed case of *disease* was recorded at *facility* at *time*.
2. **Why me:** you are the IDSR focal person for *facility / sub-county*.
3. **Now:** the steps the IDSR guidelines require (notify, investigate, collect samples),
   with links into Afiax for the case form (behind sign-in).
4. **By when:** the deadline (e.g. within 24 hours), as a date and time.
5. **Next:** what Afiax has already sent (e.g. to KHIS) and what is still manual.
6. **Help:** sub-county disease surveillance coordinator, Afiax support.

No patient names, IDs or contact details in the email.

## Data the app must supply

`diseaseName`, `caseStatus` (suspected/confirmed), `facilityName`, `subCounty`,
`recordedAt`, `notifyBy`, `caseUrl`, `alreadySubmittedTo` (list, optional).
