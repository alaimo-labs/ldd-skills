---
name: slice-this-feature
description: Break a feature spec's hypothesis into an accumulative Exposure Plan — an ordered set of 1–5 reveal levels where each level adds a visible layer of the product and tests one belief. ALWAYS use this skill when the user says "slice this feature", "slice this", "create the progressive reveal plan", "exposure plan", "divide esta feature", "plan de exposición progresiva", or shares a feature spec and asks how to reveal it in stages, how to validate it layer by layer, or how to test the hypothesis before opening the whole thing. Do NOT trigger on generic technical rollout questions (feature flag infrastructure, canary deployment tooling, CI/CD questions) — this skill designs the user-facing reveal sequence, not deployment mechanics.
---

# Slice This Feature — Accumulative Exposure Plan

You are helping the user turn a functional feature spec into an **Exposure Plan**: an ordered set of reveal levels that validate the spec's hypothesis layer by layer. Build constructs the whole feature; Reveal turns on one layer at a time.

## Core mental model

- **Build ≠ Reveal.** The team builds the complete feature. The Exposure Plan controls what becomes visible, in what order, to whom, under what belief. Feature flags are the mechanism of revelation — not a technical detail to hide, not the focus of the plan.
- **Each level accumulates.** Level 2 includes everything in Level 1. Level 3 includes Levels 1 and 2. You never remove something that was revealed; you add.
- **Each level tests one belief.** One clear falsifiable claim per level, written from the user/business perspective, never technical.
- **The set of beliefs validated across levels = the spec's hypothesis resolved.** If the hypothesis holds after the last level, the team has learned that the feature works as claimed. If a belief fails mid-plan, later levels are at risk and may be re-scoped.
- **Audience characterization, not traffic percentages.** Describe who is exposed by behavior or role ("active students with 3+ flights in the last 2 weeks"), never by technical cohort ("10% of traffic").

## Terminology (strict)

- Use **bet**, **belief**, or **assumption** for level-scoped claims — reserve "hypothesis" for the overall spec-level hypothesis being resolved.
- **Value** = desirability + utility: will users want this, use it, get something real from it?
- **Viability** = will this work for the business (economics, operations, support, legal/regulatory)?
- **Level** = one accumulative reveal step that tests one belief.
- **Validation** = the success criterion for a level. What evidence says "advance", what evidence says "stop".

If the user's input uses "hypothesis" to mean what this skill calls "belief", silently translate — don't lecture them.

## Language

Respond in the same language as the input spec. If the spec is in Spanish, produce the whole output in Spanish, using **professional neutral Spanish** — not voseo rioplatense (no "sliceá", "dividí", "tenés"; use "divide", "tiene", "se revela"). If English, English. If mixed, follow the language of the user's request, not the document.

For the section structure, follow the appropriate template:
- English input → `references/template-en.md`
- Spanish input → `references/template-es.md`

Read the template before producing output so the structure matches.

## Workflow

### Step 1 — Read the spec and extract the hypothesis

Find the hypothesis the feature is trying to resolve. It may be:
- **Explicit** — the spec has a "Hypothesis" or "Bet" section. Use it verbatim (translate silently if labeled differently).
- **Implicit** — derive it from the Overview + Success Criteria. State it in one sentence before designing levels, so the user can correct a misread.

If no spec is provided — only a one-line idea — ask the user to share the spec (problem statement, target user, core user journey, what success looks like). Don't proceed without it.

### Step 2 — Decompose the hypothesis into sequenced beliefs

A belief is one falsifiable claim that, if validated, takes the team one step closer to resolving the hypothesis. Each level tests one belief. The beliefs are ordered so that later ones only make sense if earlier ones held.

**Quality bar for a belief:**
- Written as an active-voice claim: "Students understand…", "Users act on…", "The combination of X and Y changes…"
- Falsifiable — describable evidence could make the team say "no, this didn't hold".
- User/business framing — not "the system detects patterns correctly" (technical) but "students find the detected patterns actionable enough to change what they practice next" (user).
- Load-bearing for the next level — if belief N fails, belief N+1 is at best uninterpretable and at worst irrelevant.

### Step 3 — Decide how many levels

Level count scales with the spec's scope:
- **Very small / single-capability feature:** 1 level may be enough — reveal the whole thing, validate the single belief.
- **Typical feature (multiple modules or capabilities):** 2–4 levels.
- **Large feature with several loosely-coupled modules:** up to 5 levels.
- **Never exceed 5 levels.** If 6+ feel necessary, the feature is too big for one Exposure Plan — say so in the open questions section and suggest splitting the spec.

Each level must add something **user-visible**. Not internal polish, not data pipeline work, not bug fixes. If nothing changes for the user when a level turns on, it's not a level.

### Step 4 — Write each level

For each level, specify:

- **Level name** — what's being revealed, from the user's lens. Short. Examples: "Skills progress only", "Semáforo added", "Patterns + log".
- **What is revealed** — concrete list of what's visible at this level. Be specific about what is in AND what is deliberately not yet visible (still dark).
- **Belief** — the one claim this level tests, written as a falsifiable statement in user/business terms.
- **Audience** — who is exposed, characterized by behavior or role. First levels usually small and narrow; later levels may expand. If the audience is the same as the previous level, say so and why (usually: observing the same users' behavior across beliefs reveals compound effects).
- **Duration** — how long the level stays live before deciding. Typical range: 1–3 weeks. Longer only if behavior requires observation over more cycles.
- **Validation** — the success criterion. One or two concrete thresholds or observed patterns. Include BOTH:
  - **Advance if:** what evidence says the belief held and the next level can turn on.
  - **Stop if:** what evidence says the belief didn't hold and the plan needs rework before continuing.

Keep each level dense and short. A reader should grasp the entire level in under 30 seconds. No sub-sections inside a level, no quantitative-vs-qualitative signal split, no extensive commentary.

### Step 5 — Close with parallel validations and open questions

The Exposure Plan is about value — testing whether users want/use/benefit from each added layer. Some risks to the feature are NOT testable by revealing a product layer. Those go in a separate section:

- **Parallel validations** — viability risks (operational cost at scale, regulatory exposure, channel/partner dynamics), precondition risks (does the target population have the data needed for the feature to work), or anything that needs a non-product investigation alongside the reveal. Keep each to one or two sentences.
- **Open questions for the product team** — things the plan can't resolve alone: constraints on audience recruitment, capacity of internal teams for the commitments implied, data the team already has that could reduce early risk.

Keep these sections tight. They're notes, not full investigations.

## Output format

Markdown. Follow the structure in the template (EN or ES) exactly.

Do not include preamble ("Here is the plan...") or closing fluff. The document IS the response.

## Anti-patterns — do not do these

- **Don't design levels as audience cohorts.** A level is a product layer turning on, not a different group of users being exposed. Audience may grow across levels, but what defines a level is the new thing being revealed, not who sees it.
- **Don't write a technical rollout plan.** No mention of feature flag platforms, canary infrastructure, deployment rings, or engineering sequencing. Feature flags are mentionable as the reveal mechanism — the skill focuses on what that reveal is testing, not how it's implemented.
- **Don't surface viability beliefs as levels.** Viability risks rarely validate by revealing a product layer. They go in Parallel validations.
- **Don't list every possible risk as a belief.** One belief per level. Other risks go in open questions or parallel validations, not as extra beliefs.
- **Don't produce vague validations.** "See how it goes" is not a validation. Validations have a concrete threshold or pattern and an advance/stop decision.
- **Don't reuse the spec's claims as facts.** If the spec says "users will return weekly", that's the belief to test, not a given.
- **Don't mix languages.** If the spec is in Spanish, the entire output is in Spanish, including section titles and level names.

## References

- `references/template-en.md` — English output structure
- `references/template-es.md` — Spanish output structure
- `references/examples.md` — Worked examples showing good vs. weak levels and beliefs
