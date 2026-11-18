# Training overdue

**Sent by:** Oortcloud Console, `oortcloud_console/training.py`
**Sent to:** the person whose required training is overdue (today: subject names the
person, which suggests it goes to a manager; decide and say which)
**Trigger:** weekly, for overdue required training

## Subject and preview line

- To the learner: `Reminder: {{courseCount}} required course(s) overdue`
- To a manager: `{{personName}} has overdue required training`

## Must answer

1. **What:** these required courses are overdue (list: course, due date, about how long it
   takes).
2. **Why me:** the course is required for your role (say why: onboarding, ISMS, data
   protection).
3. **Now:** open each course (direct link per course, not just the Academy home page).
4. **By when:** a new date if there is one.
5. **Next:** reminders continue weekly; what else happens (e.g. reported to manager).
6. **Help:** HR or the training lead.

## Data the app must supply

`personName`, `courses` (list of `{title, dueOn, minutes, url}`), `reason`,
`academyUrl`, `trainingContact`.
