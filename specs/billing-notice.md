# Billing notices

**Sent by:** Oortcloud Console, `oortcloud_console/billing.py`
**Sent to:** the client organisation's billing contact (or admin)
**Trigger:** invoice issued, payment due soon, payment overdue, payment received, trial
ending

Use one template with a `kind` per notice. Each notice gets its own subject.

## Must answer (all kinds)

1. **What:** the notice, with the amount in KES.
2. **Why me:** you are the billing contact for *organisation*.
3. **Now:** how to pay, with the exact details:
   - M-Pesa: paybill number, account number, amount.
   - Card / other: the Pesapal link.
4. **By when:** the due date (date, not "in 7 days").
5. **Next:** for overdue notices, exactly what happens and on what date (e.g. read-only
   access from *date*). Never threaten; state the fact. For receipts: nothing to do.
6. **Help:** billing contact at Oortcloud (email, phone), "if you've already paid, ignore
   this; payments can take up to *X* to show".

## Details box

Invoice number · Period · Amount (KES, incl. VAT) · Due date · Status · eTIMS receipt number
(when issued)

## Data the app must supply

`kind`, `organisationName`, `invoiceNumber`, `period`, `amount`, `currency`, `dueDate`,
`mpesaPaybill`, `mpesaAccount`, `pesapalUrl`, `billingUrl`, `consequence` and
`consequenceDate` (overdue only), `etimsReceipt` (optional), `billingContact`.
