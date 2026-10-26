---
name: navigation-and-flows
description: >
  Use when choosing or reviewing app navigation (tab bar, bottom navigation,
  hamburger menu, sidebar, rail), structuring information architecture, designing
  sheets, modals and dialogs flows, back behaviour, search, gestures or a
  multi-step flow such as checkout or sign-up. Do not use for form fields and
  messages (interaction-feedback-and-forms), screen spacing
  (adaptive-layout-and-spacing) or documenting site maps (ux-documentation-and-handoff).
---

# Navigation and Flows

Stance: frozen are visible location, predictable back, and standard gestures. Flexible are the pattern chosen, as long as it suits the number of destinations and the common tasks.

## Hard rules

- Use a tab bar (bottom navigation) for top-level sections only, not for actions. Mechanism: mixing actions into it confuses where the user is; put actions in a toolbar or button.
- Keep three to five top-level destinations, and never an overflow "More" for key sections. Mechanism: hidden destinations are rarely found (Apple HIG, NN/g).
- Never hide or disable a tab; show an empty state that explains. Mechanism: a tab that appears and disappears makes the interface feel unstable.
- Keep the bar visible while moving between sections. Mechanism: hiding it makes people forget where they are. A modal may cover it.
- Do not rely on a hamburger menu alone. Mechanism: low discoverability, many users never open it; add in-content routes.
- Every gesture needs a visible alternative and must not be the only route. Mechanism: voice, keyboard and switch users cannot swipe; people also do not discover hidden gestures.
- Show one sheet at a time. Mechanism: stacked sheets lose the user's place.
- Cancel dismisses, Done confirms, Back steps back. Mechanism: mixed meanings cause lost data or stuck flows.

## Gate

| Situation | Action |
|---|---|
| Two to five equal top-level sections | Tab bar or bottom navigation |
| Six or more sections, or deep content | Sidebar or hierarchical lists; keep the most used five in the bar |
| Browse-oriented, many categories | Menu plus in-content links |
| One task per visit | Hub or single flow |
| A short task needing a few inputs | Sheet |
| Long or multi-step task | Full screen flow with progress and Back |

## Steps

1. **List tasks and sections.** Write what users do, rank by frequency, group into top-level destinations.
2. **Choose the pattern** with the gate. Compact windows: bottom bar; medium: rail; expanded: sidebar (see [adaptive-layout-and-spacing](../adaptive-layout-and-spacing/SKILL.md)).
3. **Map flows.** For each key task draw entry, steps, decisions, success and error paths. Keep to the fewest steps; allow resuming.
4. **Define back and exit.** Back goes one level; a visible Back plus system back gesture. Confirm only when data would be lost.
5. **Add secondary routes.** Search where content is large, in-content links, deep links.
6. **Verify.** Walk each flow with one thumb at compact width and with a keyboard at desktop width.

## Checklist (copy into the reply and tick as you go)

```text
- [ ] Top-level destinations ranked, five or fewer in the bar
- [ ] Nav stays visible; no hidden or disabled tabs
- [ ] Back, cancel and done have one meaning each
- [ ] Each gesture has a visible alternative
- [ ] Flows mapped with success and error paths
- [ ] Navigation described per size class
```

## Examples

**Example 1: tab bar overload**
User says: "We have eight sections, can I put all eight in the bottom bar?"
Actions: rank by use; keep the top four or five; move the rest into a profile or menu screen with in-content links; explain the More tab problem.
Result: a five-destination bar and a clear home for the rest.

**Example 2: swipe-only delete**
User says: "Delete should only be a swipe left, it is cleaner."
Actions: note it is undiscoverable and unusable without gestures; keep the swipe as a shortcut, add a visible Delete in an edit mode or menu, add undo.
Result: fast path kept, nobody locked out.

## Common issues

- **Users get lost after several taps.** Cause: hidden bar or unclear titles. Fix: keep the bar visible; title every screen.
- **Back closes the app unexpectedly.** Cause: flow not pushed on a stack. Fix: define the back stack per tab.
- **Sheets nest.** Cause: an action in a sheet opens another. Fix: close the first, then open the next, or move to a full screen flow.

## Next

[interaction-feedback-and-forms](../interaction-feedback-and-forms/SKILL.md) for the controls inside flows; [ux-documentation-and-handoff](../ux-documentation-and-handoff/SKILL.md) to record the site map and flows.
