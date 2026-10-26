# Document templates

Contents: persona, user flow, site map, component state matrix, hand-off pack, prototype notes, style guide outline.

## Persona (one page)

- Name and one-line summary (a representative, not a real person)
- Context: devices, places, time pressure, hands free or not
- Goals, pain points, behaviours, accessibility needs
- Typical scenario in two or three sentences
- Evidence: which research produced this

## User flow

- Goal and entry point
- Steps in order, each with screen name and action
- Decision points and branches
- Success end and each error or exit path
- Interruptions: what happens on lost signal, a call, or leaving the app

## Site map

- Tree of top-level destinations to leaf screens
- Mark the screens in the bottom bar (compact) and how they appear in the rail or sidebar at larger sizes
- Mark deep link entry points

## Component state matrix

| State | Look | Behaviour | Copy |
|---|---|---|---|
| Default | | | |
| Pressed | | | |
| Focused | | | |
| Disabled | | reason shown | |
| Loading | | | |
| Error | | | message and fix |
| Empty | | | reason and next action |

Add: behaviour at each size class, at the largest text size, and in dark mode.

## Hand-off pack

1. Final screens with clear, consistent file names
2. Functional spec: logic, validation rules, edge cases
3. Copy deck with conditions
4. State matrix per component
5. Measurements, tokens and assets via the specs tool
6. Accessibility annotations: names, order, target sizes, contrast pairs
7. Open questions and decisions with reasons
8. A hand-off conversation with developers, and a named contact afterwards

## Prototype notes

- Purpose, audience, scope and what it does not cover
- Navigation map
- Interactive elements and expected behaviour
- Annotated screens
- Feedback received (stakeholders and tests) and changes made
- Version history

## Style guide outline

- Visual: colours (roles, both themes), type styles, icons, imagery
- Components: size, spacing and states
- Layout: grid, spacing scale, size class behaviour
- Motion: durations, easing, reduce motion
- Accessibility: contrast pairs, targets, focus indicator
