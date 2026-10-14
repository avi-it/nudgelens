# nudgelens

A Claude Code skill that audits websites and screens through six UX psychology principles, then scores them and suggests concrete fixes.

It can walk through a whole site as a first-time visitor (landing, onboarding, pricing, checkout) and stops before any irreversible step: no sign-ups, no payments, no final submits.

## The six lenses

| # | Principle | Question |
|---|-----------|----------|
| 1 | Smart defaults | Are we making users decide what we could pre-answer? |
| 2 | Goal gradient | Does progress start above zero and feel close to done? |
| 3 | Reciprocity | Do we give value before asking? |
| 4 | IKEA / endowment effect | Has the user built something before the commitment point? |
| 5 | Loss aversion | Are real stakes shown, not just benefits? |
| 6 | Contrast / anchoring | Is every cost shown against a deliberate, honest reference? |

Each principle gets a 0-3 score with a confidence level, evidence, and a specific before/after recommendation. A dark-pattern check flags deception (fake timers, confirmshaming, fake progress).

## Install

```bash
git clone https://github.com/avi-it/nudgelens.git
cp -R nudgelens/skills/ux-psychology-audit ~/.claude/skills/
```

## Use

- Single screen: share a screenshot, code, or description and ask for a UX psychology audit.
- Whole site: give a URL, e.g. "audit https://example.com with the ux-psychology-audit skill".

## Safety model for site walkthroughs

Allowed without asking: browsing, clicking CTAs, plan toggles, add to cart, reading checkout.
Needs your explicit yes: typing anything into a form.
Never: creating accounts, entering payment details or passwords, clicking final submit buttons.
Anything behind those stops is reported as "not observed" and is not scored.

## Layout

```
skills/ux-psychology-audit/
  SKILL.md
  references/   # one file per principle + site-walkthrough.md
  templates/    # audit-report.md, site-report.md
```

## Caveat

The studies cited in the references (jam, car wash, default stats) are illustrative, not guarantees. Treat recommendations as hypotheses and A/B test them.

## License

MIT
