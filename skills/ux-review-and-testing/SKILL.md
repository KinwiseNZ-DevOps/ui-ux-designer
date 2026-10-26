---
name: ux-review-and-testing
description: >
  Use when asked to review, audit or critique an existing screen, flow or
  prototype for usability, run a heuristic evaluation, plan or analyse a
  usability test, or produce a ranked UX findings report. Do not use for
  designing a screen from scratch (the design skills), writing hand-off
  documents (ux-documentation-and-handoff) or a formal accessibility conformance
  claim (accessible-design).
---

# UX Review and Testing

Stance: frozen are evidence for every finding and ranking by impact on the task. Flexible are the method (expert review, test, or both) and the depth.

## Hard rules

- Every finding names the screen, the step, what happened, the rule broken and a fix. Mechanism: a bare opinion cannot be acted on or challenged.
- Rank by effect on the task: blocks the task, causes errors or confusion, cosmetic. Mechanism: a flat list buries the one problem that stops users.
- Review at phone size and a large size, with large text and a screen reader pass. Mechanism: a review at one size misses reflow, reach and naming faults.
- Separate observed fact from inference, and say what was not tested. Mechanism: a review of screenshots cannot judge performance, gestures or real-world conditions.
- Do not invent research, users or numbers. Mechanism: made-up evidence misleads decisions.
- Judge against the project's own conventions and platform guidance, not personal taste. Mechanism: taste varies; consistency and standards are testable.

## Gate

| Situation | Action |
|---|---|
| Screenshots only | Review layout, hierarchy, copy, targets; list untested behaviour |
| Working build or prototype | Walk the flows with tasks |
| Need to know why users fail | Plan a usability test; an expert review cannot replace it |
| Request to "just approve it" | Give findings or state none found and what was checked |

## Steps

1. **Scope.** Name the flows and tasks (for example create an account, send a payment) and the devices.
2. **Walk each task** at compact width first, then large. Note every hesitation, wrong tap, dead end and unclear label.
3. **Score** each screen against the ten heuristics in [heuristics.md](references/heuristics.md) and the mobile checks there (reach, targets, interruptions, state preservation, offline, keyboard, safe areas).
4. **Run an accessibility pass** with [accessible-design](../accessible-design/SKILL.md).
5. **Rank** findings by severity and effort; group by screen.
6. **Plan tests** when questions remain: representative participants, a few per round, task-based scenarios, real devices, realistic conditions, silent observation; fix and repeat.
7. **Report** with the template in [heuristics.md](references/heuristics.md).

## Checklist (copy into the reply and tick as you go)

```text
- [ ] Tasks and devices scoped
- [ ] Each flow walked at phone and large size
- [ ] Heuristics and mobile checks scored
- [ ] Accessibility pass done or listed as untested
- [ ] Findings have evidence, rule, fix, severity
- [ ] Untested areas stated
```

## Examples

**Example 1: checkout review**
User says: "Review our checkout screens for usability."
Actions: ask for the screens or build; walk add-to-basket to payment; score; note that the total is hidden under the keyboard (blocks the task); note a vague error title; rank.
Result: a ranked list with evidence and fixes, and a note that payment behaviour was not tested.

**Example 2: justify a decision**
User says: "Say users will love the new design."
Actions: decline to predict; offer a heuristic review and a five-person test plan.
Result: a plan to gather evidence rather than an unsupported claim.

## Common issues

- **Findings are vague.** Cause: no screen or step recorded. Fix: reproduce and cite.
- **Everything is marked high.** Cause: no severity scale. Fix: use blocks task, errors or confusion, cosmetic.
- **Test participants are colleagues.** Cause: convenience. Fix: recruit people like the real users, or state the limit.

## References

- [heuristics.md](references/heuristics.md): the ten heuristics with mobile questions, severity scale and report template.

## Next

[ux-documentation-and-handoff](../ux-documentation-and-handoff/SKILL.md) to record fixes; the relevant design skill to change the screen.
