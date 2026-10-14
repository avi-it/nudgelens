# 1. Smart Defaults (vs. decision fatigue)

**Idea:** Every empty field is a decision. Too many decisions at once cause abandonment. Pre-selecting the most common choice turns "fill from scratch" into "scan and adjust", and users tend to read defaults as recommendations.

**Evidence (illustrative):** Jam study (24 flavors → ~3% bought; 6 → ~30%). Claim that 70–90% of users never change defaults. Treat as directional; the jam study has replicated inconsistently.

## Checklist
- How many fields/choices must the user complete before the primary action?
- Which fields have a most-common answer (date, quantity, country, plan, currency, time zone) that could be pre-filled?
- Can values be inferred (locale, device, previous sessions, URL params)?
- Does the primary button state the payoff (e.g. "See 12 results") instead of a bare verb ("Search")?
- Are optional fields hidden or deferred?

## Red flags
- All fields empty, all required.
- Dropdowns with a "Select…" placeholder where one option dominates.
- Long option lists with no recommended choice.
- Defaults that favor the business over the user (pre-ticked marketing opt-ins, costly add-ons). Flag these as dark patterns.

## Recommendation pattern
Pre-fill with the most common/likely value → make it obviously editable → show a payoff on the CTA → defer or remove non-essential fields.

## Scoring
0 = all blank, many choices · 1 = a few defaults by accident · 2 = good defaults but CTA/layout still ask for effort · 3 = pre-filled, editable, payoff on CTA, minimal fields
