# Sources for AI Interface Design

Contents: the books, studies and named frameworks this skill's hard rules and patterns are drawn from.

## Primary sources

- Louise Macfadyen, *Designing AI Interfaces* (O'Reilly, 2026). Input-computation-output framework; the three
  channels of intent (implicit context, explicit prompting, direct manipulation); the CARE prompt framework
  (Nielsen Norman Group); latency and wait-state design; output design principles (clear, verifiable, grounded,
  actionable, adjustable); agentic design patterns and the Reveal the Plan, Prioritize What Matters Most and
  Design for Shared Control principles.
- Lise Pilot, *AI in UX Design* (Packt, 2026). Responsible AI design principles and their mapping to the OECD
  AI Principles (OECD, 2019); AI output as hypothesis, not evidence.

## Named studies and frameworks cited in those books and relied on here

- Perez et al., "Discovering Language Model Behaviors with Model-Written Evaluations" (2022), and Sharma et
  al., "Towards Understanding Sycophancy in Language Models" (2023): models tend to mirror a user's framing
  rather than correct it.
- Liu et al., "Lost in the Middle: How Language Models Use Long Contexts" (2023): models under-attend to
  information in the middle of long prompts.
- *Mata v. Avianca* (S.D.N.Y. 2023): a real sanction for AI-hallucinated legal citations submitted without
  verification, cited as the reason output needs a verification path.
- OECD, "OECD AI Principles" (2019): the human-centred values, transparency, robustness, accountability and
  human-oversight principles this skill's hard rules translate into interface decisions.
- California SB 1001 (2019) and the EU AI Act (2024): AI-disclosure requirements in commercial and political
  contexts.
- Jakob Nielsen's response-time thresholds (0.1 s instantaneous, 1 s keeps flow uninterrupted, 10 s is about
  the limit of attention): the basis for this skill's wait-state guidance; see
  [adaptive-layout-and-spacing](../../adaptive-layout-and-spacing/SKILL.md) for other platform-sourced numbers
  used across this repo.
