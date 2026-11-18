# Services ready

**Sent by:** Oortcloud Console, `oortcloud_console/provisioning.py`
**Sent to:** the client organisation's admin
**Trigger:** provisioning finishes (the Finance site follows about 20 minutes after signup)

## Subject and preview line

- Subject: `{{organisationName}} is ready on Oortcloud`
- Preview: `Your services are set up. Here's where to start.`

## Must answer

1. **What:** everything you signed up for is ready.
2. **Why me:** you are the admin for *organisation*.
3. **Now:** one row per service: what it's for, its address, and the first thing to do
   there (e.g. Finance: "Add your company details and first item"). Then: invite your team.
4. **Need:** how to sign in (same Oortcloud account everywhere, via Afiax IAM).
5. **Next:** trial end date and what happens then.
6. **Help:** getting-started guide, Oortcloud support.

## Data the app must supply

`organisationName`, `services` (list of `{name, purpose, url, firstStep}`), `portalUrl`,
`adminEmail`, `trialEndsOn`, `supportEmail`, `helpUrl`.

Today the email lists only service names and links (`service_links`). Add `purpose` and
`firstStep` to each service definition.
