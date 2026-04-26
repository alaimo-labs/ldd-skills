# Examples — Good vs. Weak

This reference shows what good levels and beliefs look like, contrasted with weak versions.

## Beliefs — good vs. weak

### Weak belief (too vague)

> Users will want to use the dashboard.

Too generic. Not actionable — no way to say it's falsified.

### Weak belief (technical)

> The algorithm detects recurring patterns correctly.

Technical correctness, not a user/business belief. Rephrase as "Students find the detected patterns actionable enough to change what they practice next."

### Weak belief (not load-bearing)

> The 2-week window is a better default than the 4-week window.

If this is wrong, a default changes. Nothing collapses. That's an optimization, not a belief.

### Good belief (value, specific, falsifiable)

> Students return to the dashboard at least weekly without being prompted, because the readiness signals are useful enough to pull them back between flights.

Load-bearing (the whole planning frame depends on it). Specific (weekly, unprompted). Falsifiable (measurable in 2–3 weeks of exposure).

### Good belief (validates a user action, not just a perception)

> Linking an evidence-backed pattern to a block goal changes which practice the student chooses in their next flight.

Not "students feel it's useful" (perception, hard to falsify) but "changes what they choose next" (behavior, observable).

## Levels — good vs. weak

### Weak level

> **Level 1 — Beta launch.** Turn the feature on for a small group of beta testers and see how they use it.

No specific audience. No belief. "See how they use it" is not a validation. No exit criteria.

### Weak level (technical framing)

> **Level 1 — 10% rollout.** Enable for 10% of users via LaunchDarkly, monitor error rates and engagement.

Framed as deployment. "10% of users" has no user meaning. Error rates are operational, not learning signals.

### Weak level (not a new product layer, just a different audience)

> **Level 2 — Expand to more schools.** Enable the same dashboard for students at 3 additional flight schools.

Nothing new is revealed — this is distribution expansion, not a layer of the product turning on. Legitimate as part of a later level ("at wider audience") but not a level on its own.

### Good level (accumulative, one belief, validated)

> **Level 1 — Skills progress only.**
>
> What is revealed: Skills progress module with 2/4-week window toggle. Semáforo, Top 3 patterns, and block log are all still dark.
>
> **Belief:** Students can read the per-skill trend and correctly identify their weakest skill in under 2 minutes.
>
> **Audience:** 10–15 active students with at least 3 flights logged in the last 2 weeks.
>
> **Duration:** 1 week.
>
> **Validation:**
> - Advance if: ≥70% of students in short interviews correctly name their weakest skill using the module.
> - Stop if: students cannot distinguish "improving" from "stagnant" skills from the visualization — the core reading problem has to be solved before adding more modules.

Specific audience. One belief. Clear advance/stop. Short.

### Good level (adds a new layer, not just more users)

> **Level 2 — Semáforo added.**
>
> What is revealed: Readiness semáforo module now visible on top of Level 1. Top 3 patterns and log still dark.
>
> **Belief:** The semáforo changes what students choose to practice in their next flight.
>
> **Audience:** Same 10–15 students from Level 1 — observing compound effects on the same cohort.
>
> **Duration:** 1 week.
>
> **Validation:**
> - Advance if: ≥60% of students report (in a 10-minute check-in) that a semáforo call changed at least one practice decision for their next flight.
> - Stop if: students read the semáforo but their practice choices don't change — the signal isn't translating to action and expanding to patterns + log won't help.

Adds a real new layer. Reuses audience deliberately (compound learning). One belief. Observable in a check-in.
