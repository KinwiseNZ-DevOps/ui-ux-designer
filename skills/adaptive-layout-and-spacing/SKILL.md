---
name: adaptive-layout-and-spacing
description: >
  Use when laying out a screen, setting spacing and grids, handling notches and
  safe areas, adapting a phone design to tablet, foldable or desktop, choosing
  breakpoints or size classes, or fixing a layout that breaks with large text or
  rotation. Covers hierarchy, grouping, safe areas, edge-to-edge, size classes
  and reflow. Do not use for navigation structure (navigation-and-flows),
  colour and type (visual-design-system) or writing layout code.
---

# Adaptive Layout and Spacing

Stance: frozen are the information hierarchy, the full set of functions on every size, and respect for safe areas. Flexible are columns, panes and how much is shown at once.

## Hard rules

- Order by importance: key content at the top and leading edge. Mechanism: people read top to bottom from the leading side, so late placement means missed content.
- Keep functionality the same across sizes; change only how much is visible. Mechanism: a feature that exists on desktop but not on phone splits support and trust (Apple HIG).
- Design for the window, not the device. Mechanism: split screen, desktop windows, rotation and folding change available space at any time; use size classes, not device names (Android).
- Respect safe areas and system bars. Mechanism: content under the notch, status bar or gesture bar is unreadable or untappable. Inset content, keep targets out of the gesture inset.
- Layout must survive large text and 320 CSS px width without two-direction scrolling. Mechanism: WCAG 1.4.10 reflow; fixed-height boxes clip enlarged text.
- Cap line length on wide screens. Mechanism: lines across a desktop are hard to track; use a readable text width.
- Act only on what the user asked. Before answering or changing anything, open the relevant files and check what is already done; report only what you checked, never guess, and do not redo finished work. Reason: guesses and repeated work waste the user's credit.

## Gate

| Situation | Action |
|---|---|
| Small spacing or alignment tweak | Fix in place, no redesign |
| Layout fails at one size class | Fix that class, check the others |
| New screen | Phone layout first, then medium and expanded |
| Request to hide features on small screens | Decline; move them behind progressive disclosure instead |

## Steps

1. **Rank content.** List the elements on the screen and order by importance. Mark the primary action.
2. **Group and align.** Use space, containers or separators for related items. Align edges; indent only to show hierarchy. Use one spacing scale (multiples of 4 or 8) throughout.
3. **Place for the thumb.** Put frequent actions in the lower middle; keep destructive actions away from easy-hit spots. Treat reach as a heuristic: grips vary.
4. **Apply safe areas.** Pad for status bar, notch, home indicator, tab bar and keyboard. Draw backgrounds edge to edge, keep controls inside.
5. **Adapt by size class.** Use [size-classes.md](references/size-classes.md): compact (one column, bottom bar), medium (rail or two panes), expanded and larger (list-detail, sidebar, multi-column). Check height too for landscape phones and folded postures.
6. **Add desktop behaviour.** Pointer hover as an extra, visible focus, keyboard shortcuts as extras, resizable windows.
7. **Verify.** Test rotation, split screen, largest text size, 320 CSS px width, and with the keyboard open.

## Checklist (copy into the reply and tick as you go)

```text
- [ ] Content ranked; primary action obvious
- [ ] One spacing scale used
- [ ] Safe areas and keyboard handled
- [ ] Compact, medium and expanded layouts described
- [ ] Same functions at every size
- [ ] Large text and 320 CSS px tested or listed as untested
```

## Examples

**Example 1: phone to tablet**
User says: "Our order list looks stretched on iPad."
Actions: identify the window width class; keep the list as the leading pane; add a detail pane on the trailing side; keep the same actions; cap text width.
Result: a two-pane list-detail layout at medium width and above, one column on phones.

**Example 2: hiding features**
User says: "Remove the filters on mobile, nobody uses them there."
Actions: ask for evidence; explain that removal splits behaviour across sizes; propose filters behind a button opening a sheet.
Result: filters remain available, with the screen kept clean.

## Common issues

- **Content hidden behind the bottom bar.** Cause: no bottom inset. Fix: pad scrollable content by the bar height plus the safe area.
- **Fields hidden by the keyboard.** Cause: layout ignores keyboard insets. Fix: scroll the focused field into view and resize the layout.
- **Clipped labels at large text.** Cause: fixed heights. Fix: let rows grow, wrap text, test at the largest size.

## References

- [size-classes.md](references/size-classes.md): breakpoints, layout per class and desktop notes.

## Next

[navigation-and-flows](../navigation-and-flows/SKILL.md) for how navigation changes by size; [accessible-design](../accessible-design/SKILL.md) for targets and text scaling.
