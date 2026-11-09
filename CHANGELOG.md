# Changelog

All notable changes to this plugin are listed here, newest first. To cut a release, add your notes under "Unreleased", then run `python scripts/bump_version.py patch` (or `minor` or `major`). It updates the plugin version and moves those notes under the new version.

## [Unreleased]

## [0.4.0] - 2026-11-10

- Added the ai-interface-design skill, covering prompt input design, output trust and grounding, wait-state
  design for nondeterministic generation, and agentic interface patterns (reveal the plan, prioritise what
  matters most, design for shared control). Sourced from *Designing AI Interfaces* (Macfadyen, O'Reilly, 2026)
  and *AI in UX Design* (Pilot, Packt, 2026); the full annotated bibliography is in
  reference-content/sources/ai-interfaces-and-ux.md (private, not published). Routed from the router skill and
  the README diagram.
- Strengthened five existing skills with sourced detail from the same two books: interaction-feedback-and-forms
  now gives Nielsen's response-time thresholds instead of a vague wait rule and requires a reason for long or
  variable waits; mobile-ux-foundations cites the onboarding research behind its existing "keep it short" rule;
  ux-documentation-and-handoff requires AI-drafted personas and research summaries to be labelled as hypotheses
  until validated, and allows a validated prototype to stand in for part of a written spec; ux-review-and-testing
  extends its no-invented-research rule to AI-simulated personas and usability predictions.

## [0.3.0] - 2026-11-05

- Added a Works with other repos section to the router skill and README: it names the repos this one depends on or is relied on by, and when to hand off. Marketing comes first in the decision order (marketing, then look and feel, then the technical work). The map is in skills-repos-dependency-map.md beside the repos.

## [0.2.0] - 2026-10-29

- Added the rule to act only when told and to analyse the repo before answering: no guesswork, no redoing finished work, and show the real artifact when asking the user to review or approve. It is in AGENTS.md and as a hard-rule bullet in every skill.

## [0.1.0] - 2026-10-26

- Added the nine UI and UX design skills: router, mobile UX foundations, adaptive layout and spacing, navigation and flows, interaction feedback and forms, visual design system, accessible design, UX documentation and hand-off, and UX review and testing, with evals and always-on rules.
