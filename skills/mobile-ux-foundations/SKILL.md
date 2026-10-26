---
name: mobile-ux-foundations
description: >
  Use when starting or scoping a mobile app or responsive product, deciding
  what to build first, writing a design brief, planning user research, reducing
  clutter, designing onboarding, or asking how people use phones in real life.
  Covers research first, one primary action, feature prioritisation, mobile
  constraints (interruptions, one hand, weak signal) and onboarding. Do not use
  for screen layout (adaptive-layout-and-spacing), navigation choice
  (navigation-and-flows) or reviewing an existing UI (ux-review-and-testing).
---

# Mobile UX Foundations

Stance: frozen are the user's task, real-world constraints and the habit of researching before designing. Flexible are the methods, chosen to fit time and budget.

## Hard rules

- Research or observe real users before mockups. Mechanism: symptom is a polished screen nobody uses; cause is designing from the designer's own habits; fix is even a small round of interviews or a prototype test.
- One primary action per screen. Mechanism: each extra competing element on a small screen raises the effort to find the main thing; make one action visually dominant and demote the rest.
- Remove before adding. Mechanism: clutter hides the core task; cut every element that does not help the main goal, but never hide something users need to finish the task.
- Preserve state across interruptions. Mechanism: phone use is interrupted by calls, lost signal and app switching; losing a half-filled form forces a restart. Save drafts and restore position.
- Ask for permissions and set-up in context, not on first launch. Mechanism: people agree when they see why; a cold prompt gets a refusal that is hard to undo (Apple HIG onboarding).
- Do not quote old usage statistics as current. They show scale, not today's numbers.

## Gate

| Situation | Action |
|---|---|
| Users and task are unknown | Ask who, doing what, where, on which device |
| Feature request with no evidence of need | Ask what problem it solves and how it will be measured |
| Existing product with usage data | Prioritise by the most used flows first |
| Onboarding is requested | Ask whether the app can be learned by use; if so propose tips in context instead |

## Steps

1. **Frame.** Write the user, the task, the context (one hand, outdoors, queue) and the success measure in two sentences.
2. **Research.** Pick the lightest method that answers the open question: interviews, observation, a competitor walk-through, or a clickable prototype test. Record findings as short personas and a main user flow.
3. **Prioritise.** List features, mark which serve the core task, cut or defer the rest. Refine the most used first.
4. **Design for constraints.** For each flow ask: what if the signal drops, the user is interrupted, uses one thumb, or has the text size increased? Add draft saving, offline messages and a way back.
5. **Onboard lightly.** Default to no tutorial. If needed: short, skippable, interactive, with later access in help. Postpone non-essential set-up and give sensible defaults.
6. **Record** decisions and reasons using [ux-documentation-and-handoff](../ux-documentation-and-handoff/SKILL.md).

## Checklist (copy into the reply and tick as you go)

```text
- [ ] User, task, context and success measure stated
- [ ] Research method chosen to fit the open question
- [ ] Features ranked; core task protected; extras deferred
- [ ] One primary action per screen
- [ ] Interruption, weak signal and one-hand cases handled
- [ ] Onboarding optional, short and in context
```

## Examples

**Example 1: scoping a new app**
User says: "We're building a household budgeting app. What should the first version include?"
Actions: ask who uses it and when; frame the core task (record spending in seconds, see what is left); rank features; propose three interviews and a prototype test; flag draft saving for half-entered transactions.
Result: a short brief with the core flow, deferred features and a research plan.

**Example 2: a five-screen tutorial**
User says: "Add a five-screen tutorial on first launch explaining everything."
Actions: explain that long tutorials are skipped and forgotten; propose a skippable single screen at most, plus context tips on first use of each feature, plus a help entry.
Result: onboarding that teaches by doing, without blocking first use.

## Common issues

- **Stakeholders keep adding features.** Cause: no stated core task. Fix: write the core task first and score every request against it.
- **Research is skipped for time.** Cause: it seems slow. Fix: test a rough prototype with three people; it still beats none.
- **The home screen has five equal buttons.** Cause: no priority. Fix: pick the main action, make it dominant and group the rest.

## Next

[navigation-and-flows](../navigation-and-flows/SKILL.md) once the core flow is known; [ux-review-and-testing](../ux-review-and-testing/SKILL.md) to check the result.
