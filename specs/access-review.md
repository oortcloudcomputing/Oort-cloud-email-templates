# Access review due or overdue

**Sent by:** Oortcloud Console, `oortcloud_console/reviews.py`
**Sent to:** the reviewers of an access review
**Trigger:** a review opens, and weekly while it's overdue

## Subject and preview line

- Opened: `Access review: {{count}} people to check by {{dueOn}}`
- Overdue: `Overdue: access review for {{reviewTitle}}`

## Must answer

1. **What:** a review of who has access to *system* is open, with *n* people still to
   decide.
2. **Why me:** you are a named reviewer (for staff, part of the ISMS access-control
   process).
3. **Now:** 1. Open the review. 2. For each person, keep or remove access. 3. Submit.
4. **By when:** due date. Roughly how long it takes (about a minute per person).
5. **Next:** nothing is removed automatically (true today); overdue reviews are reported
   to *whom*.
6. **Help:** the security lead.

## Data the app must supply

`reviewTitle`, `systemName`, `undecidedCount`, `dueOn`, `reviewUrl`, `isOverdue`,
`securityContact`.
