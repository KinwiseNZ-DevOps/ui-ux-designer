---
name: visual-design-system
description: >
  Use when choosing or reviewing typography, type scale, colour palette, dark
  mode, icons, imagery, elevation, a spacing scale, design tokens or a style
  guide for a mobile or responsive product. Do not use for a full accessibility
  audit (accessible-design), screen layout (adaptive-layout-and-spacing) or
  brand strategy and illustration.
---

# Visual Design System

Stance: frozen are legibility, semantic colour roles and consistency with the platform. Flexible are brand colours, typeface and personality, within contrast and scaling limits.

## Hard rules

- Use text styles that scale with system settings, not fixed pixel sizes. Mechanism: people who enlarge text get nothing from hard-coded sizes. Apple's default is 17 pt on iPhone with an 11 pt floor (Apple HIG); Toptal recommends no smaller than 11 pt.
- Meet contrast: 4.5:1 for normal text, 3:1 for large text (18 pt, or bold) and for controls and icons that carry meaning. Mechanism: WCAG 1.4.3 and 1.4.11; low contrast fails in sunlight and for low vision.
- Check contrast in light and dark separately. Mechanism: a pair that passes in light often fails inverted.
- Name colours by role (background, surface, text, accent, danger), not by hue. Mechanism: role tokens map cleanly to dark mode and rebranding; hue names break.
- Never use colour alone for meaning; add an icon, text or shape. Mechanism: colour-blind users and bright glare lose the signal.
- Prefer platform system fonts and colours unless the brand needs otherwise. Mechanism: they adapt to Dynamic Type, Increase Contrast and dark mode for free.
- Use one spacing scale and one icon style. Mechanism: mixed values read as errors and slow scanning.
- Avoid light font weights at small sizes. Mechanism: thin strokes disappear first on small, low-resolution or bright screens.
- Act only on what the user asked. Before answering or changing anything, open the relevant files and check what is already done; report only what you checked, never guess, and do not redo finished work. Reason: guesses and repeated work waste the user's credit.

## Gate

| Situation | Action |
|---|---|
| Project already has tokens | Use them; add only what is missing, with reasons |
| No system exists | Propose a minimal set: type scale, colour roles, spacing scale, radii, elevation, icon set |
| Brand colour fails contrast | Keep brand for large shapes; use a darker or lighter shade for text and controls |
| Request for pixel-perfect fixed type | Explain scaling; give sizes as starting values for text styles |

## Steps

1. **Detect.** Read the existing tokens, theme file and components. List the typeface, sizes, colours.
2. **Type.** Define styles (title, headline, body, caption, label) with size, weight and line height; looser leading for long text; allow wrapping and growth.
3. **Colour.** Define roles for light and dark; compute contrast for each text and control pair using a calculator; mark status colours with an icon.
4. **Space and shape.** Define the spacing scale (multiples of 4 or 8), corner radii and elevation levels; keep touch areas independent of visible size.
5. **Icons and imagery.** One set, one stroke weight, labelled where meaning is unclear; provide alt text for informative images.
6. **Record** tokens and rules in a style guide (see [ux-documentation-and-handoff](../ux-documentation-and-handoff/SKILL.md)).
7. **Verify** at the largest text size, in dark mode, with Increase Contrast, and in bright light on a real phone if possible.

## Checklist (copy into the reply and tick as you go)

```text
- [ ] Text styles scale; no fixed sizes
- [ ] Contrast computed for every text and control pair, in both themes
- [ ] Colours named by role
- [ ] Meaning never carried by colour alone
- [ ] One spacing scale, one icon style
- [ ] Tokens recorded
```

## Examples

**Example 1: brand colour on white**
User says: "Our brand light green with white text on buttons, can we use it?"
Actions: compute the ratio; if below 4.5:1 propose a darker green for the button fill (or dark text on the light green); keep the light green for decoration.
Result: brand feel kept, buttons readable.

**Example 2: invert for dark mode**
User says: "Just invert the colours for dark mode."
Actions: explain that inversion breaks contrast and elevation cues; define role tokens for dark and check each pair.
Result: a proper dark theme with verified contrast.

## Common issues

- **Colours look fine on the design screen, washed out outdoors.** Cause: marginal contrast. Fix: raise to at least the AA ratios, preferably higher for key text.
- **Text overflows at large sizes.** Cause: fixed heights. Fix: allow growth and test at the largest setting.
- **Status shown by red and green only.** Cause: colour-only signal. Fix: add icon and text.

## Next

[accessible-design](../accessible-design/SKILL.md) for the full check; [interaction-feedback-and-forms](../interaction-feedback-and-forms/SKILL.md) for state styling.
