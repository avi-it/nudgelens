# UX Psychology Audit: TaskNest (demo site, http://localhost:8765)

**Date:** 2026-10-14 · **Audited as:** first-time visitor · **Method:** live walkthrough, stopped before irreversible steps

## Verdict
TaskNest asks for a lot and gives nothing back. Signup is a 7-field blank form behind a "0% complete" bar, the board is locked until an account exists, and checkout pre-ticks an upsell and shames the exit. Only the pricing page is partly sound. Biggest opportunity: let visitors use the product before the account wall.

## Journey log

### Landing → Signup
| Step | Screen | Asked of user | Given to user | Notes |
|------|--------|---------------|---------------|-------|
| 1 | `/index.html` | Click "Sign up" | Tagline only | "Try the board: Create an account to try the board." The trial itself is the gate |
| 2 | `/signup.html` | 4 text fields + 3 dropdowns | Nothing | Progress bar reads "0% complete"; all dropdowns say "Select..."; newsletter box ticked by default |

**Stopped at:** signup form, nothing entered, "Sign up" not clicked (account creation is off-limits). **Not observed:** onboarding after signup.

### Pricing → Checkout
| Step | Screen | Asked of user | Given to user | Notes |
|------|--------|---------------|---------------|-------|
| 3 | `/pricing.html` | Pick a plan | $9 / $29 / $99 listed, no highlight | No recommended plan |
| 4 | `/checkout.html?plan=team` | Card number, "Pay now" | Order summary | "Priority Support $15/month" pre-ticked; exit link says "...lose my team's data in 7 days" |

**Stopped at:** checkout, card field untouched, "Pay now" not clicked. **Not observed:** payment confirmation, any real data-loss mechanics.

## Scorecard

| Principle | Score | Confidence | Evidence | Top fix |
|-----------|-------|------------|----------|---------|
| 1. Smart defaults | **1/3** | High | Steps 2, 4 | Pre-select country/time zone/size from locale; un-tick the upsell |
| 2. Goal gradient | **0/3** | High | Step 2 | A "0% complete" bar over a 7-field form is deflating; credit the first field or split into steps |
| 3. Reciprocity | **0/3** | High | Steps 1, 2 | Nothing is given before the ask; open a sandbox board without signup |
| 4. IKEA / endowment | **0/3** | High | Steps 1, 2 | Nothing belongs to the user at the account wall; let them name a project first |
| 5. Loss aversion | **1/3** | Medium | Step 4 | Loss framing exists but is unverifiable and shaming (see ethics note) |
| 6. Contrast / anchoring | **2/3** | Medium | Step 3 | Three tiers give a usable anchor, but no plan is highlighted and the $15 add-on is shown outside plan context |

**Overall: 0.7 / 3** · Not scored: post-signup onboarding, payment confirmation.

## Findings

### Smart defaults
- **Experienced:** three dropdowns start at "Select..." although country and time zone are detectable. The newsletter checkbox ("product updates and partner offers") is pre-ticked, and so is the $15/month Priority Support add-on.
- **Why it matters:** blank choices create decision fatigue; pre-ticked extras are a dark pattern, not a smart default.
- **Change:** detect country/time zone, default company size to the most common value, un-tick marketing and upsell by default.
- **Example:** `Country: Romania (detected)` instead of `Select...`.
- **Ethics note:** pre-ticked paid add-on is a dark pattern: remove.

### Goal gradient
- **Experienced:** signup opens with a progress bar at "0% complete".
- **Change:** split into 2 steps (email + password, then profile) and show step 1 already counted, or drop the bar if it can't start above zero honestly.
- **Example:** "Step 1 of 3: you're 33% there" once the email is entered.

### Reciprocity
- **Experienced:** the homepage promises "Try the board" but requires an account to do it.
- **Change:** show a read-only sample board or a sandbox that works without signup, then ask to save it.
- **Example:** "Save this board: create a free account" after the user has added a task.

### IKEA / endowment
- **Experienced:** no choice or creation happens before the account wall, so closing the tab costs nothing.
- **Change:** ask "Name your first project" and show the empty board before asking for an email.

### Loss aversion
- **Experienced:** the exit link says "I'll stay on the free plan and lose my team's data in 7 days".
- **Why it matters:** a concrete loss beats a gain, but only if true and specific.
- **Change:** if the 7-day limit is real, say what exactly is lost ("12 tasks and 3 members in Project Alpha will be archived on Oct 21") and use neutral exit copy.
- **Ethics note:** if the deadline isn't real this is a fake-urgency dark pattern; the exit copy is also confirmshaming-adjacent.

### Contrast / anchoring
- **Experienced:** three tiers ($9 / $29 / $99) with no highlighted plan; the $15 add-on appears only at checkout.
- **Change:** highlight Team as recommended, and show the add-on as a plan-relative amount ("+52% on Team").

## Dark-pattern sweep
1. Pre-ticked paid add-on ($15/month) at checkout.
2. Pre-ticked marketing opt-in at signup.
3. Exit link combines shaming and an unverifiable data-loss claim.

## Priority roadmap
1. **Quick wins:** un-tick the upsell and marketing box; neutral exit copy; detect country/time zone.
2. **Medium:** split signup into steps; highlight a recommended plan.
3. **Bigger bet:** sandbox board before the account wall.

## Suggested A/B tests
- Sandbox board vs. signup-first → signup conversion.
- 7-field vs. 2-step signup → form completion rate.
- Un-ticked vs. pre-ticked add-on → revenue per checkout *and* refund/complaint rate.

## Limits of this audit
Everything after the account wall and the real payment step was not observed. Demo site is static, so no real data-loss or trial mechanics exist.
