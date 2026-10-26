# Size classes and layout per class

Contents: width classes, height classes, layout per class, desktop notes, edge-to-edge notes.

## Width classes (Android window size classes, official)

| Class | Width | Typical window |
|---|---|---|
| Compact | under 600 dp | phone in portrait |
| Medium | 600 to under 840 dp | tablet in portrait, large unfolded phone |
| Expanded | 840 to under 1200 dp | tablet in landscape |
| Large | 1200 to under 1600 dp | large tablet display |
| Extra-large | 1600 dp and above | desktop display |

## Height classes

| Class | Height | Typical window |
|---|---|---|
| Compact | under 480 dp | phone in landscape |
| Medium | 480 to under 900 dp | tablet landscape, phone portrait |
| Expanded | 900 dp and above | tablet portrait |

Width usually decides the layout. Check height when the window is medium width but compact height: a two-pane layout will not fit comfortably.

Apple expresses the same idea as compact and regular size classes on iPhone and iPad; keep the layout recognisable for the platform when resized.

## Layout per class (design guidance, partly inference)

| Class | Layout | Navigation |
|---|---|---|
| Compact | one column, full-width content, sheets for secondary tasks | bottom bar (3 to 5 destinations) |
| Medium | one or two panes, wider cards, optional side panel | navigation rail |
| Expanded and larger | list-detail or multi-column, persistent filters | rail or permanent sidebar |
| Extra-large | same as expanded with a capped content width, extra margins | sidebar |

Rules: do not add or remove functions between classes; do reveal actions that were behind an overflow menu when space allows; keep the primary action in a consistent place.

## Desktop notes

- Pointer: hover is an extra signal, never the only one. Provide right-click or menu alternatives where expected.
- Keyboard: tab order follows visual order; focus is visible and not hidden behind sticky bars (WCAG 2.4.11).
- Windows resize freely: test narrow widths down to 320 CSS px (reflow).
- Line length: keep readable text to a comfortable measure rather than the full width.

## Edge-to-edge and system bars (Android guidance)

- Android 15 and later enforce edge-to-edge. Draw behind transparent bars and use window insets to inset content.
- Keep touch targets out of the gesture bar area.
- Sync layout with the on-screen keyboard.
- Immersive modes (video) must let a tap reveal the bars again.
