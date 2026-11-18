# Writing Afiax and Oortcloud emails

This guide is for anyone who writes or changes an email that one of our apps sends: the
Afiax Clinical Suite, the Oortcloud Console, Finance, HR, the Academy, or the alerts the
Kenya country pack sends. Read it before you write a new email or change the words of an
existing one.

The emails themselves live in [`emails/`](emails/). The plan for each email (who gets it,
what it says, what data it needs) lives in [`specs/`](specs/).

## The rule: answer the reader's questions before they ask

Most people open an email on a phone, between other things. If they have to reply to ask
"what is this?" or "what do I do now?", the email has failed.

Every email must answer these six questions. Use the checklist at the bottom of this page
before you ship.

| # | Question | What to write | Where it goes |
|---|---|---|---|
| 1 | **What happened?** | One plain sentence. Name the person, organisation and thing involved. | Heading and first line |
| 2 | **Why did I get this, and is it real?** | Say how we know them: "your clinic admin added you", "you asked to reset your password". | First paragraph |
| 3 | **What do I do now?** | Numbered steps, one action each. Put the button inside step 1, not floating on its own. | Steps |
| 4 | **What do I need, and by when?** | Anything they must have ready (phone, M-Pesa, ID number) and any deadline or expiry, as a real date and time in EAT. | Details box, steps |
| 5 | **What happens next?** | What they will see after they act, and what happens if they don't. | "What happens next" |
| 6 | **Who can help, and what if this wasn't me?** | A named person first (their admin), Afiax support second. Tell them what to do if they didn't expect this. | Help box, security note |

Not every email needs every section. A receipt has no steps. But every email must answer
all six questions somewhere, even if the answer is one line.

## The parts of an email

Every email is built from the same parts, in this order. Use the ones you need and leave
the rest out.

1. **Subject.** Says what happened, with the most specific name first. At most about 60
   characters so it fits on a phone.
   - Good: `Jane Wanjiku invited you to Nairobi West Clinic on Afiax`
   - Bad: `Afiax Connected Healthcare — Welcome`
2. **Preview line.** The grey line inboxes show after the subject. Use it for the action
   and the deadline: `Set your password to get started.` Never leave it empty, or the inbox
   shows "View in browser" or the first words of the footer.
3. **Heading.** The subject again in fewer words.
4. **Summary paragraph.** Questions 1 and 2 in two or three sentences.
5. **Details box.** A short table of facts the reader might need to find later:
   organisation, role, amount, invoice number, due date, who sent it. Four to six rows.
6. **Steps.** A numbered list. Each step starts with a bold verb: **Set your password**,
   **Sign in**, **Pay**. The main button sits inside the first step.
7. **What happens next.** One short paragraph.
8. **Help box.** Who to contact. Their admin first, by name, if we know it. Afiax support
   second.
9. **Security note.** Small text. "Not expecting this?" and what to do.
10. **Footer.** Added by the layout. You don't write it.

Every email is sent twice in one message: as designed HTML and as plain text. Write the
plain-text version with the same parts in the same order. Some people only ever see the
plain text (some screen readers, some phones, some work mail filters).

## How to write

- **Plain words.** Write for someone who has never used Afiax and is not technical. Say
  "sign in", not "authenticate". Say "your clinic", not "your project" or "your tenant".
- **Short sentences.** One idea each. If a sentence has "and" twice, split it.
- **Talk to the reader.** "You", "your". Say who did what: "Jane added you", not "you have
  been added".
- **Real dates and times.** "25 Nov 2026, 17:00 EAT", not "in 7 days" or "soon". Times are
  East Africa Time unless the reader's organisation says otherwise.
- **Never promise what the system doesn't do.** If a link doesn't expire, don't say it
  expires. If we don't know who sent an invite, leave that line out rather than guessing.
  Check the code (see each spec's "Data" section) before you write a fact.
- **No internal names.** Never write Medplum, Frappe, ERPNext, Zitadel, Mifos, Zulip,
  "project", "tenant", "membership" or "access policy" in an email. Use the product names in
  the [brand guide](#names-to-use).
- **One main button.** If there are two things to do, the second is a text link.
- **Every button has a plain link under it.** Some mail apps hide buttons. Write "If the
  button doesn't work, copy this link into your browser:" and the full address.

## Patient data and privacy

Email is not a safe place for health information. Mail sits in phones, laptops and
providers' logs for years, and subject lines show on lock screens.

- **Never put patient names, ID numbers, diagnoses, results or prescriptions in an email**,
  and never in a subject line. Say what kind of thing happened and link into the app, where
  the reader has to sign in to see it.
  - Good: `Security alert: emergency access used at Nairobi West Clinic`
  - Bad: `Break-glass access — John Kamau — Nairobi West Clinic`
- Public-health alerts may name the disease and the area, because the people who get them
  need that to act. They must not name or identify a patient.
- Don't attach documents that contain patient data.

This follows the Kenya Data Protection Act and the Digital Health Act. If you are not sure
whether something counts as patient data, leave it out and link to the app.

## Security wording

People are taught to distrust emails with links. Help them trust ours:

- Tell them why they got it (question 2).
- Show the address the link goes to, as plain text, under the button.
- In every email with a sign-in or password link, add: "Afiax will never ask for your
  password by email or phone."
- For anything involving a password, sign-in or email change, tell them what to do if it
  wasn't them, and that nothing has changed until they act (when that's true).

## Names to use

| Say | Not |
|---|---|
| Afiax | Afiax Connected Healthcare (except in the footer), Medplum |
| your clinic / your organisation / *its name* | project, tenant, workspace |
| your role, *role name* | access policy, membership, profile |
| sign in, sign out | log in, log on, authenticate |
| Oortcloud Console | Frappe, Desk |
| Finance | ERPNext |
| Afiax Pay | Mifos, Fineract |
| two-step sign-in | MFA, 2FA, TOTP |

## Tone by kind of email

| Kind | Tone | Examples |
|---|---|---|
| Welcome and invites | Warm, practical | Invite, signup confirmation, services ready |
| Account security | Calm, precise, no alarm | Password reset, email change, new sign-in |
| Money | Exact, neutral, never threatening | Invoice, receipt, payment overdue |
| Clinical and public-health alerts | Short, factual, action first | Break-glass, outbreak, IDSR |
| Reminders | Friendly, specific | Training overdue, access review due |

## Before you ship: checklist

- [ ] The subject names the specific person, organisation or thing, and fits in about 60
      characters.
- [ ] The preview line says the action and any deadline.
- [ ] All six questions are answered.
- [ ] Every fact (expiry, amount, role, what happens next) is checked against the code.
- [ ] No patient names, IDs or clinical details anywhere, especially the subject.
- [ ] No internal product names.
- [ ] Every button has a plain link under it.
- [ ] The plain-text version has the same content as the HTML.
- [ ] You looked at it in the preview (`npm run build:emails`, then open `dist/preview/`) in
      light and dark mode and at phone width.
- [ ] The spec in `specs/` matches what you wrote.

## How the files work

- `emails/<name>.mjml` is the designed HTML version, written in [MJML](https://mjml.io).
- `emails/<name>.txt` is the plain-text version.
- `emails/<name>.json` holds the subject, and sample data used for the previews.
- `emails/partials/` holds the brand: fonts, colours, header and footer. Change those once
  and every email follows.

The words in `{{double braces}}` are filled in by the app when it sends. They use
[Mustache](https://mustache.github.io/mustache.5.html) and only these forms:

| Form | Meaning |
|---|---|
| `{{name}}` | Insert a value. In the HTML it is made safe (so `<` can't become a tag). |
| `{{#name}} … {{/name}}` | Show this part only if `name` is set. If `name` is a list, repeat it for each item. |
| `{{^name}} … {{/name}}` | Show this part only if `name` is **not** set. |
| `{{! note }}` | A note for writers. Never sent. |

Keep logic out of the templates. If you need "if this and that", ask the developer to add a
single yes/no value to the data instead.

`npm run build:emails` turns the sources into `dist/`:

- `dist/afiax/<name>.html` and `.txt`: the files the apps use.
- `dist/preview/<name>--<sample>.html`: each email filled with its sample data, to look at.
- `dist/node/email-templates.ts`: the same templates as one TypeScript file, copied into
  the Afiax Clinical Suite server.
