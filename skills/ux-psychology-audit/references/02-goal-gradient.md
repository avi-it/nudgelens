# 2. Goal Gradient Effect (endowed progress)

**Idea:** The closer people feel to finishing, the faster they move. You can choose where the starting line is: credit real prior actions so progress never starts at 0%.

**Evidence (illustrative):** Car-wash loyalty card study: 10 stamps with 2 pre-filled was completed at nearly double the rate of an 8-stamp empty card, though both needed 8 purchases. LinkedIn's profile-strength meter never starts at zero.

## Checklist
- Does the flow show progress at all (steps, percent, checklist)?
- Does it start above 0%? Is there a real action to credit (account created, email entered, first selection)?
- Is the number of steps small and honest? Are steps of similar effort?
- Is the remaining work visible and bounded ("2 steps left")?
- Is the first step easy enough to complete immediately?

## Red flags
- "0% complete" with many empty steps.
- No progress indicator in a multi-step flow.
- Progress that jumps backward or stalls.
- Fake progress: crediting steps the user did not do, or bars that mislead about remaining effort. Flag as a dark pattern.

## Recommendation pattern
Count something already done as step 1 → show progress from the first screen → put the easiest step first → show what's left.

## Scoring
0 = no progress cues or starts at zero in a long flow · 1 = progress exists but starts at 0 · 2 = some head start, unclear remainder · 3 = honest head start, bounded steps, visible momentum
