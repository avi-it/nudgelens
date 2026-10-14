---
name: ux-psychology-audit
description: Audit a screen, flow, or product against six UX psychology principles (smart defaults, goal gradient, reciprocity, IKEA/endowment effect, loss aversion, contrast/anchoring). Use when the user asks to review, critique, or improve onboarding, signup, checkout, pricing, upsell, or form screens from a psychology or conversion angle, or mentions decision fatigue, defaults, progress bars, paywalls, or persuasion in UX. Works on screenshots, URLs, code, or written descriptions.
---

# UX Psychology Audit

Evaluate a UI against six principles and produce concrete before/after recommendations.

## Principles (details in `references/`)

| # | Principle | Core question | Reference |
|---|-----------|---------------|-----------|
| 1 | Smart defaults | Does the user face blank decisions that we could pre-answer? | `references/01-smart-defaults.md` |
| 2 | Goal gradient | Does progress start above zero and feel close to done? | `references/02-goal-gradient.md` |
| 3 | Reciprocity | Do we give real value before asking for anything? | `references/03-reciprocity.md` |
| 4 | IKEA / endowment effect | Has the user built or "owned" something before the commitment point? | `references/04-ikea-endowment.md` |
| 5 | Loss aversion | Are we framing what the user loses, not just what they could gain? | `references/05-loss-aversion.md` |
| 6 | Contrast / anchoring | Is every price or cost shown against a deliberate reference? | `references/06-contrast-anchoring.md` |

## Modes

- **Single screen / flow** (screenshot, code, description): use the workflow below.
- **Whole website** (user gives a URL and wants the full experience audited, e.g. "analyze this site", "go through their signup and checkout"): read `references/site-walkthrough.md` first and report with `templates/site-report.md`. In this mode you actively click through the site as a first-time visitor, through landing, onboarding, pricing, and checkout, but you **stop before any irreversible step** (no account creation, no payment, no final submit, no real personal data entered). Scores are based on what you actually experienced, with a confidence level, and unobserved steps are listed as such.

## Workflow

1. **Identify the input and scope.** Screenshot, URL, code, or description. If it's a URL, open it with a browser tool; if it's a multi-step flow, list the steps first. Ask only if you can't tell which screen or goal (signup, purchase, upgrade, etc.) is being analyzed.
2. **Determine relevance.** Not every principle applies to every screen. Mark each as `Applies`, `Partly`, or `N/A` with one line of reasoning. Do not force a finding where the principle has no purchase.
3. **Read the reference file** for each principle that applies. Use its checklist and red flags.
4. **Score each applicable principle** 0–3:
   - 0 = absent or counterproductive
   - 1 = weak or accidental
   - 2 = present but improvable
   - 3 = well executed
5. **Write recommendations.** For each principle scoring ≤2, give a specific change: what the screen does now, what it should do, and an example of the new copy or UI. Tie it to the actual elements on the screen, never generic advice.
6. **Prioritize.** Rank the recommendations by expected impact on the screen's goal metric and by implementation effort. Name the top 3.
7. **Output** using `templates/audit-report.md`.

## Rules

- Be specific. Quote real labels, field counts, prices, and button text from the input.
- Separate observation (what's on the screen) from inference (what it probably does to the user).
- Treat the numbers in the references (jam study, car wash, 70–90% defaults, etc.) as illustrative, not proven facts. Do not present them as guaranteed effects for this product. Recommend A/B testing for anything that changes conversion-critical flows.
- Ethics check: if a recommendation relies on deception (fake countdowns, false scarcity, fake progress that isn't earned), flag it as a dark pattern and offer an honest alternative. Loss framing must reflect a real loss, and progress credit must reflect something the user actually did.
- If comparing two versions (before/after), score both and report the delta per principle.
- Reply in the user's language.

## Quick mode

If the user asks for a fast take, skip the full report: give a 6-line table (principle, score, one-line fix) and the top recommendation.
