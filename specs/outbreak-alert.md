# Outbreak alert

**Sent by:** Afiax Clinical Suite server, `packages/server/src/country-pack/kenya/outbreak.ts`
**Sent to:** public-health contacts configured for the organisation or county
**Trigger:** an outbreak rule detects a cluster (cases over a threshold within a window)

## Subject and preview line

- Subject: `Public health alert: {{diseaseName}}, {{caseCount}} cases in {{windowDays}} days, {{placeLabel}}`
  (this is close to today's subject and is fine: no patient data).
- Preview: `Review the cases and decide whether to notify the county.`

## Must answer

1. **What:** the rule that fired, in plain words, with the case count, window and place.
2. **Why me:** you are a public-health contact for *place/organisation*.
3. **Now:** 1. Open the case list in Afiax (behind sign-in). 2. Confirm or dismiss the
   alert. 3. If confirmed, notify the county as required (say how, and whether Afiax
   already did: link to the IDSR spec).
4. **By when:** the reporting deadline for this disease.
5. **Next:** what Afiax does automatically (e.g. KHIS/IDSR submission), and what it doesn't.
6. **Help:** county disease surveillance coordinator (if known), Afiax support.

## Details box

Disease · Cases · Period · Area · Rule · Detected at

No patient names or IDs. Counts and area only.

## Data the app must supply

`diseaseName`, `ruleDescription`, `caseCount`, `windowDays`, `periodStart`, `periodEnd`,
`placeLabel`, `detectedAt`, `caseListUrl`, `reportingDeadline`, `countyContact` (optional).
