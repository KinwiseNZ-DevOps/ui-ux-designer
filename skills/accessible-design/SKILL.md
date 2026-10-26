---
name: accessible-design
description: >
  Use when checking or designing for accessibility on mobile, tablet or desktop:
  touch target size, contrast, text scaling, screen readers (VoiceOver,
  TalkBack), keyboard and switch use, reduce motion, WCAG 2.2 criteria, or an
  accessibility checklist for a design. Do not use for general visual styling
  (visual-design-system), legal compliance claims, or writing accessibility
  code for a framework.
---

# Accessible Design

Stance: frozen are WCAG 2.2 AA as the floor, platform minimums for touch, and no information carried by one sense only. Flexible are how each requirement is met in a given design.

## Hard rules

- Touch targets: 44 x 44 pt on iOS (28 pt hard minimum), 48 x 48 dp on Android and the web, 8 dp apart; WCAG 2.2 AA floor is 24 x 24 CSS px or 24 px of spacing. Mechanism: small or crowded targets cause mis-taps and exclude people with tremor; the visible icon may be smaller if the hit area is padded.
- Contrast 4.5:1 for text and 3:1 for large text and meaningful controls (WCAG 1.4.3, 1.4.11). Mechanism: low contrast fails low vision and glare.
- Text must scale to large sizes and reflow at 320 CSS px without clipping (WCAG 1.4.4, 1.4.10). Mechanism: fixed-height boxes cut off enlarged text.
- Every control has a name, role and state a screen reader can announce; reading order follows visual order. Mechanism: unlabeled icon buttons are silent or read as "button".
- Do not rely on gestures, drags or multi-finger input alone; give a single-tap or button path (WCAG 2.5.7). Mechanism: switch, voice and keyboard users cannot perform them.
- Focus is always visible and not hidden behind sticky bars (WCAG 2.4.11). Mechanism: keyboard and switch users lose their place.
- Never use colour, sound, haptics or motion as the only signal. Mechanism: each fails for some users; pair them.
- Sign-in must not demand memory tests, puzzles or transcription without alternatives (WCAG 3.3.8). Mechanism: cognitive load blocks access; allow paste, password managers and passkeys.
- State accessibility claims as "meets criterion X at level AA" with the check made; never "fully accessible" or "compliant". Mechanism: conformance needs scope and evidence.

## Gate

| Situation | Action |
|---|---|
| Quick design check | Run the checklist; mark untested items |
| Formal audit requested | Say what an automated and manual check cover; recommend testing with disabled users; no compliance claim |
| A hard-to-hit control needed (dense map pins) | Treat as the "essential" exception; offer an alternative way |
| Request to drop a requirement for looks | Offer a design that keeps the requirement (padded hit area, darker shade) |

## Steps

1. **Targets.** Measure hit areas, not visuals. Use [targets-and-contrast.md](references/targets-and-contrast.md).
2. **Contrast.** Compute ratios for text, icons, borders and focus rings, in each theme.
3. **Text scaling.** Check largest system size and browser zoom to 400 percent.
4. **Screen reader pass.** Name every control; set order; group; mark decorative images; announce state changes.
5. **Input alternatives.** Check one-finger, keyboard, switch and voice paths for each task.
6. **Motion and time.** Honour reduce motion; avoid flashing; allow extensions on time limits.
7. **Errors and help.** Identify the field, explain the fix; keep help in a consistent place (WCAG 3.2.6).
8. **Report** what passed, failed and was not tested, with the criterion for each.

## Checklist (copy into the reply and tick as you go)

```text
- [ ] Targets sized and spaced per platform
- [ ] Contrast checked in each theme
- [ ] Largest text and 320 CSS px tested
- [ ] Names, roles, order set for a screen reader
- [ ] Single-pointer alternative for gestures and drags
- [ ] Visible focus, not obscured
- [ ] No signal carried by one sense only
- [ ] Authentication has an alternative
- [ ] Untested items listed
```

## Examples

**Example 1: icon toolbar**
User says: "Check this toolbar of five 24 px icons for accessibility."
Actions: measure hit areas; propose 48 dp padded areas with 8 dp gaps; require accessible names for each icon; check icon contrast at 3:1.
Result: a list of failures with fixes and criterion numbers.

**Example 2: ask for a certificate**
User says: "Tell me this app is WCAG compliant."
Actions: decline a blanket claim; state which criteria were checked and how; list untested areas.
Result: an honest scoped statement.

## Common issues

- **Icon buttons read as just "button".** Cause: no accessible name. Fix: add a label matching the visible meaning.
- **Large text breaks the layout.** Cause: fixed heights. Fix: allow growth and wrap.
- **Custom control invisible to a screen reader.** Cause: no role or state exposed. Fix: use the platform control or expose role, name and value.

## References

- [targets-and-contrast.md](references/targets-and-contrast.md): target sizes, contrast values and WCAG 2.2 mobile criteria.

## Next

[ux-review-and-testing](../ux-review-and-testing/SKILL.md) to run the checks with real users.
