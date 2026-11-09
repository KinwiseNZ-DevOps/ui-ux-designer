---
name: interaction-feedback-and-forms
description: >
  Use when designing forms and input, validation, error messages, alerts and
  confirmations, loading, empty and error states, buttons, haptics, toasts,
  microinteractions or motion, or login and sign-up screens. Do not use for
  navigation structure (navigation-and-flows), colour and type
  (visual-design-system) or a full accessibility audit (accessible-design).
---

# Interaction, Feedback and Forms

Stance: frozen are honest status, recoverable mistakes and optional motion. Flexible are the exact wording, channel and animation, as long as the user always knows what happened and what to do next.

## Hard rules

- Every action gets feedback. Mechanism: without it people wonder whether a tap worked and tap again. Use more than one channel (visual change, text, haptic or sound) so screen reader users and those with sound off still get it.
- Match interruption to importance. Mechanism: status should be quiet and near what it describes; only data-loss or critical issues should interrupt. Overused alerts get ignored.
- Warn only for unexpected, irreversible loss. Mechanism: warning on every undoable delete trains people to dismiss warnings. Offer undo instead.
- Keep a visible label on every field. Mechanism: placeholder text disappears when typing, leaving people unsure what the field is.
- Show the right keyboard and validate at the right time. Mechanism: wrong keyboards add taps; validating too early scolds people mid-typing. Check email on leaving the field; check passwords and usernames as they are created.
- Preserve entered data after an error or interruption. Mechanism: losing a form is the fastest way to lose a user.
- Error text says what, why and how to fix, in plain words. Mechanism: "Error" or a code gives no route to recovery.
- Do not make people re-enter data, memorise codes or solve puzzles to sign in. Mechanism: WCAG 3.3.7 and 3.3.8; allow paste, password managers and passkeys.
- Drag and complex gestures need a single tap alternative (WCAG 2.5.7).
- Motion is brief, purposeful and optional; honour reduce motion. Mechanism: gratuitous motion distracts and can cause discomfort; important information must not rely on it.
- A wait always communicates something, even silence. Mechanism: Nielsen's response-time thresholds (0.1 s feels instant, no feedback needed; 1 s is the limit before people notice but their train of thought holds, feedback optional; past 10 s people's attention wanders and a progress indicator or time estimate becomes necessary) set when an indicator is required, not optional polish. An unexplained long wait reads as the product being unreliable even when the delay is normal.
- When a wait is long or its length varies (a report, an export, anything generated rather than fetched), say why it is taking time, not just that it is. Mechanism: a bare spinner with no explanation is read as doubt about whether the request worked at all; a short reason ("Preparing your export...") keeps trust through the delay.
- Act only on what the user asked. Before answering or changing anything, open the relevant files and check what is already done; report only what you checked, never guess, and do not redo finished work. Reason: guesses and repeated work waste the user's credit.

## Gate

| Situation | Action |
|---|---|
| Info that needs no action | Passive inline status, not an alert |
| Undoable destructive action | Do it and offer undo |
| Irreversible, uncommon destructive action | Confirmation with a clearly named destructive button |
| Wait under 0.1 s | No indicator needed; feels instant |
| Wait 0.1-1 s | Indicator optional; the interaction still feels continuous |
| Wait 1-10 s | Skeleton or placeholder, plus a determinate progress bar when length is known, a spinner when it is not |
| Wait over 10 s | Progress or a time estimate is required, not optional; say why it is taking time |

## Steps

1. **List interactions** on the screen and what changes after each.
2. **Define states** for each control: default, pressed, focused, disabled (with a reason), loading, success, error.
3. **Design forms.** One column, labels above, fields sized to content, only required fields, defaults filled, correct keyboard type, autofill hints, secure fields for secrets, a single clear primary button.
4. **Write messages.** Inline error beside the field plus a summary for long forms; specific titles; neutral tone; one action.
5. **Design the empty, loading and error screens.** Say why it is empty and offer the next action; pick the loading pattern by expected length (see the Gate table); for a wait over 10 s or one of variable length, say what is happening, not only that something is; offer retry with preserved data on failure.
6. **Add motion sparingly.** Short transitions that explain where things came from; no animation on frequent actions; provide reduce motion version.
7. **Verify** with a slow network, no network, a screen reader and large text.

## Checklist (copy into the reply and tick as you go)

```text
- [ ] Each action has visible feedback, plus a second channel
- [ ] Alerts only for actionable or irreversible cases
- [ ] Labels visible; keyboard types set; validation timing chosen
- [ ] Errors say what, why and fix; data preserved
- [ ] Empty, loading and error states written
- [ ] Loading pattern matches wait length; waits over 10 s or of variable length explain why
- [ ] Motion short, optional, reduce motion handled
```

## Examples

**Example 1: sign-up form**
User says: "Design a sign-up screen with email, password and confirm password."
Actions: remove confirm password in favour of a show-password toggle; label each field; email keyboard; allow paste and password manager; validate email on exit; error text explains the rule; keep typed email after an error.
Result: a short form that passes the authentication and redundant-entry criteria.

**Example 2: alert for everything**
User says: "Show a popup when an item is saved, deleted and when the app opens."
Actions: replace save with a brief inline confirmation or haptic; delete with undo; remove the open alert, show any news in place.
Result: interruptions reserved for what needs a decision.

## Common issues

- **Users double-submit.** Cause: no pressed or loading state. Fix: disable and show progress, keep label.
- **Error message disappears too fast.** Cause: timed toast. Fix: keep errors until fixed; place beside the field.
- **Disabled button with no reason.** Cause: unexplained rule. Fix: keep it enabled and explain on tap, or state the missing item.

## Next

[visual-design-system](../visual-design-system/SKILL.md) for how states look; [accessible-design](../accessible-design/SKILL.md) to check names, focus and contrast; [ai-interface-design](../ai-interface-design/SKILL.md) when the wait is for an AI-generated result, where length is often unpredictable and the content itself needs a way to be checked.
