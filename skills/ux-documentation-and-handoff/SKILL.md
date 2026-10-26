---
name: ux-documentation-and-handoff
description: >
  Use when writing UX documentation for an app: personas, user flows, site maps,
  wireframe and prototype notes, a style guide, component state specs, design
  principles, or a developer hand-off pack. Do not use for choosing the design
  itself (the design skills), for running usability tests
  (ux-review-and-testing) or for software documentation such as a README.
---

# UX Documentation and Hand-off

Stance: frozen are a single source of truth, versioned records, and specs that describe behaviour, not just looks. Flexible are the format and tool, and how many of the document types a project needs.

## Hard rules

- Describe behaviour and states, not only pictures. Mechanism: a static mockup hides what happens on error, loading, empty, long text and large text; developers then guess.
- Use real copy, not placeholders, with notes on when each message appears. Mechanism: lorem ipsum hides length and tone problems, and developers end up writing copy.
- Keep one living set of documents with version history. Mechanism: stale copies in chat and email lead to building the wrong version.
- Record the reason for each decision. Mechanism: later changes can be checked against the original intent.
- Specify behaviour for each size class and for large text. Mechanism: a phone-only spec leaves tablet and desktop to improvisation.
- Include accessibility annotations: names, reading order, target sizes, contrast pairs. Mechanism: added late they are rarely added at all.
- Mark timing advice as guidance, not rule. Mechanism: projects vary; the sources give typical order only.

## Gate

| Situation | Action |
|---|---|
| Small change to one screen | Update the affected spec and changelog only |
| New product or major flow | Produce the full set in the order below |
| No time for everything | Keep flows, states, style guide and hand-off notes; drop the rest |
| Developers already have a spec tool | Use it; do not create a second source |

## Steps

1. **Research documents.** Methods used, personas (goals, pain points, behaviour, scenarios), user flows with entry points, decisions, success and error paths.
2. **Information architecture.** Site map of screens and sections, content groups, navigation paths.
3. **Design deliverables.** Wireframes for structure, mockups for visuals, prototypes for interaction; annotate each.
4. **Principles and style guide.** Shared priorities; colour, type, icons, components with states, layout and responsive rules, motion, accessibility.
5. **Interaction patterns.** Navigation, input, feedback, microinteractions, transitions, in the project's own words.
6. **Prototype notes.** Purpose, audience, scope, navigation, behaviour, feedback received and changes made.
7. **Hand-off pack.** Final named screens, functional spec, copy, state matrix, specs tool link, open questions, a call with developers. Templates: [document-templates.md](references/document-templates.md).
8. **Version.** Date, author and change summary on every release of the documents.

## Checklist (copy into the reply and tick as you go)

```text
- [ ] Personas and flows reflect research, not guesses
- [ ] Site map matches the built navigation
- [ ] Every component has all states specified
- [ ] Behaviour given per size class and at large text
- [ ] Real copy included with display conditions
- [ ] Accessibility annotations added
- [ ] Version history and open questions recorded
```

## Examples

**Example 1: hand-off pack**
User says: "Write the hand-off notes for the new transfer screen."
Actions: list screens and flows; state matrix for amount field, buttons and result; copy with conditions; size class behaviour; accessibility names; call out open questions.
Result: a pack that lets developers build without asking about every case.

**Example 2: placeholder copy**
User says: "Just leave lorem ipsum in the error messages, we will fill them later."
Actions: explain the cost; draft real messages from the error cases and ask the owner to approve.
Result: copy that fits the layout and is ready to build.

## Common issues

- **Developers ask the same questions repeatedly.** Cause: missing states and edge cases. Fix: add the state matrix and error paths.
- **Docs and product drift apart.** Cause: no owner or version. Fix: name an owner and update with each release.
- **The site map and real navigation differ.** Cause: changes made in the app only. Fix: update the map in the same change.

## References

- [document-templates.md](references/document-templates.md): outlines for each document type.

## Next

[ux-review-and-testing](../ux-review-and-testing/SKILL.md) to test the documented design.
