# Targets, contrast and WCAG 2.2 criteria

Contents: target sizes, spacing, contrast values, WCAG 2.2 criteria that matter on mobile, testing tools.

## Touch target sizes

| Source | Recommended | Minimum |
|---|---|---|
| Apple HIG, iOS and iPadOS | 44 x 44 pt | 28 x 28 pt |
| Apple HIG, macOS | 28 x 28 pt | 20 x 20 pt |
| Apple HIG, visionOS | 60 x 60 pt | 28 x 28 pt |
| Android accessibility help | 48 x 48 dp (about 9 mm) | keep 48 |
| web.dev | about 48 CSS px, 8 px apart | |
| WCAG 2.2 SC 2.5.8, Level AA | | 24 x 24 CSS px, or a 24 px circle around the target not touching another |
| WCAG 2.2 SC 2.5.5, Level AAA | | 44 x 44 CSS px |

Spacing: Apple suggests about 12 pt around bezelled controls and 24 pt around borderless ones. Android suggests 8 dp between targets.

Exceptions to 2.5.8: spacing, an equivalent control on the page, inline links in text, browser-controlled controls, essential size.

Technique: keep the visible icon small and pad the hit area (padding, minimum size, or an enlarged touch area). On the web, enlarge only for touch with the coarse pointer media query.

## Contrast

| Item | Minimum ratio | Criterion |
|---|---|---|
| Text up to 17 pt (not bold) | 4.5:1 | 1.4.3 AA |
| Text 18 pt and above, or bold | 3:1 | 1.4.3 AA |
| Icons, input borders, focus indicators | 3:1 | 1.4.11 AA |
| Disabled controls | exempt, but keep them recognisable | |

Support Increase Contrast and test both light and dark themes.

## WCAG 2.2 criteria with mobile impact

| Criterion | Level | Plain meaning |
|---|---|---|
| 1.4.4 Resize Text | AA | text can reach 200 percent without loss |
| 1.4.10 Reflow | AA | works at 320 CSS px wide, no two-way scrolling (maps, tables, video exempt) |
| 2.4.11 Focus Not Obscured (Minimum) | AA | focused item not fully hidden by sticky content |
| 2.5.7 Dragging Movements | AA | any drag has a single-pointer alternative |
| 2.5.8 Target Size (Minimum) | AA | 24 x 24 CSS px or spacing |
| 3.2.6 Consistent Help | A | help options stay in the same relative place |
| 3.3.7 Redundant Entry | A | do not ask for the same information twice in one process |
| 3.3.8 Accessible Authentication (Minimum) | AA | no memory test, puzzle or transcription without an alternative |

W3C has no separate mobile standard: WCAG 2 applies to mobile web, native and hybrid apps, and a WCAG2Mobile draft explains how.

## Testing tools

- Android: Accessibility Scanner, TalkBack, Espresso accessibility checks.
- iOS: Accessibility Inspector, VoiceOver, Dynamic Type and Increase Contrast settings.
- Web: browser zoom to 400 percent, keyboard-only pass, contrast checker.
- Real users with disabilities give evidence automated tools cannot.
