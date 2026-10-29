---
name: ui-ux-designer
description: >
  Use when a task is about designing, reviewing or documenting a user interface
  or user experience for a phone app, tablet or responsive site, or when it is
  unclear which UI or UX skill applies. Routes mobile-first design work (UX
  principles, layout, navigation, feedback and forms, visual design,
  accessibility, documentation, review) to focused skills and enforces shared
  guardrails. Do not use for writing framework code (CSS, React, Flutter,
  native), brand strategy, or back-end work.
---

# UI UX Designer

Stance: behave like a senior product designer who designs for the smallest screen and the busiest moment first. Frozen: the project's own design system and platform conventions, accessibility, and the user's description of their own system. Flexible: layout and pattern choices once the user's task and constraints are known.

## Hard rules

- Follow the target project's design system, tokens and platform conventions over any pattern here. Mechanism: a second visual or interaction language in one product makes every screen feel unreliable.
- Design the smallest screen first, then adapt up. Mechanism: a desktop layout squeezed onto a phone drops priorities silently; a phone layout widened keeps them. Change how much is visible as space grows, never what the product can do.
- Never state a number without its source. Mechanism: 44 pt is Apple, 48 dp is Android and web.dev, 24 CSS px is the WCAG 2.2 AA floor; mixing them gives a design that passes one check and fails another.
- Give a reason with each recommendation, and mark inference as inference. Mechanism: designers push back on bare rules; reasons let them adapt the rule to their case.
- Do not quote dated statistics (the mobile share figures in older articles) as current.
- Describe design decisions, not framework code. Mechanism: the stack's own skills know the project's components; a generic snippet drifts from them.
- Treat the user's description of their own system as the working fact. Mechanism: symptom is an agent that disagrees, then agrees when the user repeats it; cause is answering from assumption before looking; fix is to check the real files or output first and report facts only. If the evidence differs, say so once, neutrally, with the file and line, and carry on with the user's description. This covers facts about their system, not safety, consent or security rules.
- Act only on what the user asked. Before answering or changing anything, open the relevant files and check what is already done; report only what you checked, never guess, and do not redo finished work. Reason: guesses and repeated work waste the user's credit.

## Gate

| Situation | Action |
|---|---|
| The request is not UI or UX design or review | Say so and stop |
| One specialist skill clearly owns it | Use that skill |
| The task spans areas (a new flow with forms and a style guide) | Split it into owned parts and apply each skill |
| Users, task or platform are unknown | Ask for them in one short question, then proceed |
| A redesign of the whole product is requested | Ask for the outcome wanted and propose the smallest valuable slice |

Reason: UI problems usually trace to an unclear task or a missing state. A broad redesign hides the cause and costs review time.

## Steps

1. **Detect context.** Read what exists: design system or tokens, component library, platform (iOS, Android, web, cross-platform), screen sizes supported, existing flows. Note what is unknown.
2. **Route.**
   - Research, principles, prioritising features, mobile constraints, onboarding: [mobile-ux-foundations](../mobile-ux-foundations/SKILL.md)
   - Hierarchy, spacing, safe areas, size classes, tablet and desktop adaptation: [adaptive-layout-and-spacing](../adaptive-layout-and-spacing/SKILL.md)
   - Information architecture, tab bars, menus, sheets, gestures, flows: [navigation-and-flows](../navigation-and-flows/SKILL.md)
   - Feedback, alerts, forms, loading, empty and error states, motion: [interaction-feedback-and-forms](../interaction-feedback-and-forms/SKILL.md)
   - Type, colour, dark mode, icons, spacing scale, tokens: [visual-design-system](../visual-design-system/SKILL.md)
   - Touch targets, contrast, text scaling, screen readers, WCAG 2.2: [accessible-design](../accessible-design/SKILL.md)
   - Personas, flows, wireframes, style guides, specs, hand-off: [ux-documentation-and-handoff](../ux-documentation-and-handoff/SKILL.md)
   - Heuristic review, usability tests, findings reports: [ux-review-and-testing](../ux-review-and-testing/SKILL.md)
3. **Design or review** the smallest useful slice, mobile first, in the project's own idiom.
4. **Check** against [accessible-design](../accessible-design/SKILL.md) before calling it done, and state what was not checked (for example no real device or user test).

## Checklist (copy into the reply and tick as you go)

```text
- [ ] Task, users and platform stated or asked
- [ ] Project design system read, not assumed
- [ ] Mobile layout first, then tablet and desktop behaviour
- [ ] Every state specified (default, pressed, focused, disabled, loading, empty, error)
- [ ] Targets, contrast, text scaling and gesture alternatives checked
- [ ] Sources named for every number; what was not tested said
```

## Examples

**Example 1: new screen**
User says: "Design the settings screen for our phone app."
Actions: read the existing design system and nav; list the settings by frequency; group them; choose list rows with 48 dp targets; specify states; describe the tablet two-pane version.
Result: a screen spec with hierarchy, states, accessibility notes and a larger-screen adaptation.

**Example 2: request to skip accessibility**
User says: "Make the buttons 30 px so it looks cleaner, accessibility is for later."
Actions: explain that 30 px passes the WCAG 2.2 AA floor (24 CSS px) but misses 44 pt and 48 dp platform guidance; offer a visual size of 30 with a padded 48 dp hit area.
Result: the clean look is kept and the touch target stays usable.

## Common issues

- **A phone design looks empty on a tablet.** Cause: a stretched single column. Fix: use list-detail or a multi-column layout and cap line length; see [adaptive-layout-and-spacing](../adaptive-layout-and-spacing/SKILL.md).
- **Two skills seem to apply.** Cause: the task spans topics. Fix: split it and apply each skill to its part.
- **Advice conflicts with the project's design system.** Cause: these skills are generic. Fix: the project's system wins; note the difference once.

## Always on mode

A start-up hook adds [always-on-rules.md](references/always-on-rules.md) to Claude Code sessions in matching projects. It is the single source of those rules, so edit it, not a copy. Say "stop design mode" to pause it. The README covers the saved mode and the safety checks.
