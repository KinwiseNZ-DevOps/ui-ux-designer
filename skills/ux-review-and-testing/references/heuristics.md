# Heuristics, severity and report template

Contents: ten heuristics with mobile questions, mobile checks, severity scale, usability test notes, report template.

## Ten usability heuristics (Nielsen Norman Group)

| Heuristic | Mobile questions |
|---|---|
| 1 Visibility of system status | Is progress shown? Does a tap give instant feedback? Is offline or sync status clear? |
| 2 Match with the real world | Are words the user's own? Is the order logical? |
| 3 User control and freedom | Is there undo? A visible Back? Can a flow be cancelled without losing data? |
| 4 Consistency and standards | Does it follow platform patterns (tab bar, sheet, back)? Same words for same things? |
| 5 Error prevention | Are inputs constrained? Right keyboard? Confirmation only for irreversible actions? |
| 6 Recognition rather than recall | Are options visible? Are recent items and defaults offered? |
| 7 Flexibility and efficiency | Shortcuts, saved details, autofill, bulk actions? |
| 8 Minimalist design | One primary action? Anything that could go? |
| 9 Error recovery | Does the message say what, why, how to fix? Is entered data kept? |
| 10 Help and documentation | Is help in context and task-based? |

Mobile research on heuristics is sparse, so these are extended with the checks below rather than replaced.

## Mobile checks

- Reach: are frequent actions comfortable with one thumb? Are destructive ones away from easy-hit spots?
- Targets: sized and spaced to platform minimums.
- Interruptions: is state kept after a call, background, or lost signal?
- Offline and slow network: sensible messages, queued actions.
- Keyboard: right type, fields not hidden, next-field order.
- Safe areas: notch, home indicator, bars.
- Large text and dark mode.
- Single-window flow: can a task finish without leaving the app?
- Desktop: keyboard, focus, hover as extra.

## Severity scale

| Level | Meaning |
|---|---|
| 1 Blocks task | User cannot complete the task or is likely to lose data |
| 2 Errors or confusion | User completes with errors, delay or help |
| 3 Cosmetic | Noticeable but does not affect the task |

## Usability test notes

- Recruit people like the real users; a handful per round finds the main problems; repeat after fixes (long-standing NN/g guidance).
- Give tasks as goals, not instructions. Observe silently. Note where people hesitate, tap wrongly or give up.
- Use real devices, one-handed and in realistic conditions.
- Record findings and design changes in the prototype notes.

## Report template

```text
Scope: flows, devices, build or screenshots, date
Method: expert review / test, participants if any
Not tested: list

Finding 1 (severity 1)
Where: screen and step
What happened:
Rule: heuristic or criterion
Evidence: screenshot or quote
Fix:
```
