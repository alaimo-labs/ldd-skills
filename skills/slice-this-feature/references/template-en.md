# Exposure Plan — [Feature name]

## Spec hypothesis

One sentence. If the spec explicitly states a "Hypothesis" or "Bet", reproduce it here. If not, infer it from the Overview + Success Criteria in one sentence, and note that it's an inference.

## Reveal mechanism

**Recommendation:** [Progressive reveal (feature flags) | Incremental development]

**Why:** [one or two signals that drove the choice — e.g., "Levels 1–2 target specific student cohorts, which requires flag-based audience targeting" or "All levels expose to the full user base; assuming the coding agent maintains context across iterations, layers can ship as built"]

Suggestion only — engineering owns the final implementation choice.

## Levels

Each level accumulates on the previous. Level 2 includes everything in Level 1. Level 3 includes Levels 1 and 2. The team builds the full feature; the layers get revealed in this order.

### Level 1 — [Name from the user's perspective]

What is revealed: [concrete list of what's visible; what is deliberately still dark]

**Belief:** [one falsifiable claim in user/business terms]

**Audience:** [characterized by behavior or role, not by traffic percentage]

**Duration:** [time before deciding]

**Validation:**
- **Advance if:** [concrete threshold or pattern]
- **Stop if:** [concrete threshold or pattern]

### Level 2 — [Name]

What is revealed: [new layer added on top of prior level]

**Belief:** [...]

**Audience:** [...]

**Duration:** [...]

**Validation:**
- **Advance if:** [...]
- **Stop if:** [...]

[...continue based on spec scope. A single level if the feature is very small. Up to 5 if very large. Typically 2–4.]

## Parallel validations

Risks that can't be tested by revealing a product layer, but run alongside the plan:

- **[Short title]:** [1–2 sentences — what to investigate, why it matters]
- **[Short title]:** [...]

## Open questions for the product team

- [Constraint, data point, or decision the plan can't resolve alone]
- [...]
