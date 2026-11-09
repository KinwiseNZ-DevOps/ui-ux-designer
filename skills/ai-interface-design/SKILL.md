---
name: ai-interface-design
description: >
  Use when designing or reviewing the user-facing interface of a feature
  powered by an AI model: a chat or assistant, a copilot layered on an
  existing tool, an AI-generated output (text, image, summary), or an
  autonomous or semi-autonomous agent. Covers prompt input design, trust and
  verifiability of AI output, waiting states for nondeterministic latency,
  and agentic interface patterns (plan visibility, shared control). Do not
  use for prompt engineering or model selection for accuracy (an engineering
  concern), for training or evaluating a model, or for a product with no AI
  component (the other design skills).
---

# AI Interface Design

Stance: behave like a designer who treats every AI feature as probabilistic, not deterministic, and designs
accordingly. Frozen: AI output is never presented as a settled answer; every claim a user might act on has a
way to verify it or a human in the loop; the user stays able to see, interrupt and reverse what an agent does.
Flexible: how much of the model's internal process to reveal, and which input and output patterns fit the
product.

## Hard rules

- Never present AI output as a final answer. Give every claim a user might act on a way to verify it (a
  citation, a source, a human-review step) or hedge the language; never show a bare confidence percentage as if
  it were an inspectable error count. Mechanism: an LLM's "confidence" is a next-token probability, not a
  checkable fact, so a bare number manufactures trust it has not earned.
- Make the AI's grounding visible: which source, locale, mode or prior context shaped this answer, not only
  what the answer says. Mechanism: the same question can have a different correct answer depending on
  jurisdiction, time or context the user cannot see; a short "why we suggested this" affordance prevents a
  wrong answer being applied in the wrong context.
- Design the wait state deliberately; never leave a long or variable delay with no signal. Mechanism: silence
  during a delay still communicates something to the user, usually doubt, so an unexplained wait reads as the
  product being unreliable even when the delay is normal.
- For a feature that acts rather than only answers (an agent, a tool-using assistant): reveal its plan before
  it spends time or makes a change, keep it interruptible while it works, and make its actions reversible.
  Mechanism: autonomy that cannot be seen, paused or undone feels like replacement, not assistance, and a wrong
  plan caught early costs nothing to fix.
- Do not add an AI feature without a reason beyond "the capability exists." Mechanism: an AI feature that adds
  complexity without a clear user benefit erodes trust in every other AI feature in the product.
- Disclose that a user is talking to or reading output from an AI where that is not obvious from context.
  Mechanism: several jurisdictions require this (for example California's SB 1001, the EU AI Act); users who
  do not know make different, worse-informed decisions.
- Never state a number, study or named pattern without its source, matching the router's existing rule.
  Mechanism: see [sources.md](references/sources.md) for the sourcing behind every claim and pattern in this
  skill.
- Act only on what the user asked. Before answering or changing anything, open the relevant files and check
  what is already done; report only what you checked, never guess. Reason: guesses and repeated work waste the
  user's credit.

## Gate

| Situation | Action |
|---|---|
| Designing input, output, latency or trust for an AI feature | Use this skill |
| Choosing or tuning the model itself, prompt engineering for accuracy, training or evals | Hand off to engineering; this skill covers the interface only |
| An agent or tool-using assistant that takes actions, not just answers | Use this skill's agentic steps; weight Design for Shared Control highest |
| No AI component in the request | Route to the matching sibling skill instead |
| Request to hide that content is AI-generated, or to show a fabricated confidence score | Decline; explain the disclosure and verifiability rules; offer a compliant alternative |

## Steps

1. **Classify the interaction.** Is it a model only (replies to a prompt), a tool-using assistant (acts in the
   world when the user directs it), or an agent (plans and acts with some autonomy)? Each layer needs more
   interface transparency and control than the one before it.
2. **Design the input.** Identify which of the three intent channels carry the request: implicit context (what
   is open or selected), explicit prompting (typed or spoken), direct manipulation (buttons, sliders,
   selection). Make the context the system is using visible; offer structured input (templates, mode selectors)
   for well-defined tasks and free text for exploration; let preconfigured actions teach what is askable without
   implying they are the only options.
3. **Design the wait.** Pick the base loading pattern by length with [interaction-feedback-and-forms](../interaction-feedback-and-forms/SKILL.md).
   Then add what generation needs beyond that: streaming partial output as it is produced rather than a single
   reveal; a visible plan and tiered status (overview, detail, full record) once the task is agentic; state why
   the wait is happening, since a generated result's length is often unpredictable and a silent long wait reads
   as failure.
4. **Design the output.** Make it clear (structured, scannable), verifiable (a trail the user can check or a
   human-review step), grounded (source, locale, mode visible), actionable (a clear next step, and whether it
   is final or reviewable before it is taken) and adjustable (refine in place rather than forcing a restart).
5. **For an agent:** reveal the plan before it executes; prioritise which status information actually matters
   at each moment rather than showing everything; design for shared control (interruptible, reversible, explicit
   confirmation at the risk points, a stated boundary on how long it may act unsupervised).
6. **Check** against [accessible-design](../accessible-design/SKILL.md) and this skill's hard rules before
   calling it done; state what was not tested (for example no real users, no engineering review of the
   underlying model).

## Checklist (copy into the reply and tick as you go)

```text
- [ ] Interaction classified: model, tool-using assistant or agent
- [ ] Input channels identified; context the system is using is visible
- [ ] Wait state designed on purpose, not left as a bare spinner
- [ ] Output gives a way to verify or a human-review step for any claim acted on
- [ ] Grounding (source, locale, mode) visible, not just the answer
- [ ] AI involvement disclosed where not obvious
- [ ] For an agent: plan shown first, interruptible, reversible, confirmation at risk points
- [ ] Sources named for every number or pattern; what was not tested stated
```

## Examples

**Example 1: a document-summary assistant**
User says: "Design the UI for a feature that summarises an uploaded contract."
Actions: show the file and page range being read (grounding); stream the summary rather than show a bare
spinner; attach the summary to quoted source passages the user can expand to check (verifiability); offer
"shorter," "more detail," and "flag risks" as refinement actions on the existing summary rather than forcing a
new upload; disclose that the summary is AI-generated and may miss nuance a lawyer would catch.
Result: a summary the user can trust exactly as far as it has earned, with an easy way to check it.

**Example 2: request to fake certainty**
User says: "Add a confidence percentage next to each AI answer so it looks more trustworthy."
Actions: explain that an LLM's confidence is a token probability, not an inspectable accuracy score, so a bare
percentage would mislead users rather than inform them; offer the alternative that actually serves the goal:
visible sources, a "why we suggested this" explainer, or a human-review step for anything the user will act on.
Result: the trust the stakeholder wants, built on a mechanism that can actually carry it.

## Common issues

- **The chat box gets treated like a search bar.** Cause: it looks like one, so users bring 25 years of search
  habits that do not apply to prompting. Fix: structured input options (templates, mode selectors, example
  chips) teach what to type without relying on the user to already know.
- **A big spinner sits over a response that is already streaming in.** Cause: latency UI copied from a
  traditional loading state. Fix: match the indicator to what else is visible; a large indicator is redundant
  once reasoning, a plan or the first line of text is already on screen.
- **An agent's actions feel like a surprise.** Cause: no plan was shown before it started, or it could not be
  paused. Fix: reveal the plan first and keep the agent interruptible and its actions reversible.

## References

- [sources.md](references/sources.md): the books, studies and named frameworks this skill draws on.

## Next

[accessible-design](../accessible-design/SKILL.md) for touch targets, contrast and screen reader support, which
apply to an AI feature exactly as to any other. [interaction-feedback-and-forms](../interaction-feedback-and-forms/SKILL.md)
for general loading, empty and error state patterns this skill builds on. [ux-documentation-and-handoff](../ux-documentation-and-handoff/SKILL.md)
to write up an AI feature's states and disclosure copy for hand-off.
