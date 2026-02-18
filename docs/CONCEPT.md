<!-- TEMPLATE INSTRUCTIONS
  FILE: CONCEPT.md
  PURPOSE: Captures the founding vision for the project in plain language. This document
  answers "what is this and why does it exist?" before any technical or feature detail is
  introduced. It should be readable by a non-technical stakeholder and should remain stable
  across development — it is a north-star reference, not a task list.

  HOW TO CUSTOMIZE:
  - Replace all [PLACEHOLDER] tokens with the real terms for your project.
  - Delete any section that is genuinely not applicable (e.g. delete the Idle/Passive Play
    section entirely if your project has no passive-play dimension).
  - Keep the language high-level. If you find yourself writing acceptance criteria or
    implementation details, those belong in PRD.md or ADDITIONAL.md.
  - Revisit this document at the start of each milestone to confirm the vision is still
    accurate. If it has drifted, update it rather than leaving it stale.
-->

# [PROJECT_NAME] — Project Vision

---

## Goal / Vision

[PROJECT_NAME] is a [GENRE/CATEGORY] [PRODUCT_TYPE] that [one-sentence description of the
core player or user experience]. The project aims to [primary design goal] while ensuring
that [secondary design goal, e.g. accessibility, low-friction onboarding, satisfying
long-term progression].

**Design pillars:**

1. **[PILLAR_1]** — [One sentence describing what this pillar means in practice.]
2. **[PILLAR_2]** — [One sentence describing what this pillar means in practice.]
3. **[PILLAR_3]** — [One sentence describing what this pillar means in practice.]

---

## Core Loop / Main User Flow

The core loop is the fundamental action cycle the user repeats throughout their session.
It must feel rewarding on its own, independent of any meta-progression layer.

```
[ACTION_1] → [OUTCOME_1] → [ACTION_2] → [OUTCOME_2] → (repeat)
```

**Step-by-step:**

1. The user [ACTION_1, e.g. "opens the application and observes the current state"].
2. The user [ACTION_2, e.g. "makes a meaningful decision based on available resources"].
3. The decision produces [OUTCOME, e.g. "an immediate reward or a queued result"].
4. The reward enables [NEXT_STEP, e.g. "the user to take a more powerful action"].
5. After [TIME_OR_CONDITION], the user [LOOP_RETURN, e.g. "returns to step 1 with more
   resources than before"].

---

## Idle / Passive Play

> **NOTE TO AUTHOR:** Delete this entire section if your project has no idle or passive
> dimension. This section is specifically for products that continue to produce output when
> the user is not actively engaged.

When the user is not actively present, [PROJECT_NAME] continues to [PASSIVE_ACTIVITY,
e.g. "accumulate resources"] at a rate determined by [RATE_DRIVER, e.g. "the current
configuration the user left behind"].

- Passive accumulation is capped at [TIME_CAP] to prevent exploitation and preserve
  the value of active sessions.
- Upon returning, the user is shown [RETURN_SUMMARY, e.g. "a summary of what was
  earned in their absence"] and can [RETURN_ACTION, e.g. "spend those resources
  immediately"].
- Passive rates are always lower than active rates to reward engagement.

---

## Resources and Rates

The economy is built around [NUMBER] primary resource types. All rates are expressed in
[RESOURCE_UNIT] per [TIME_UNIT].

| Resource | Symbol | Description | Primary Source |
|----------|--------|-------------|---------------|
| [RESOURCE_1] | [R1] | [What it represents, e.g. "the main spendable currency"] | [How it is earned] |
| [RESOURCE_2] | [R2] | [What it represents, e.g. "a secondary premium currency"] | [How it is earned] |
| [RESOURCE_3] | [R3] | [What it represents, e.g. "a prestige/rebirth currency"] | [How it is earned] |

**Key rate drivers:**

- [DRIVER_1]: [How this factor affects production rates]
- [DRIVER_2]: [How this factor affects production rates]
- [DRIVER_3]: [How this factor affects production rates]

---

## Types of [DOMAIN_ENTITY]

[DOMAIN_ENTITY] is the central object the user builds, manages, or interacts with.
There are [NUMBER] categories:

### [CATEGORY_1_NAME]

[Description of this category. What does it do? What niche does it fill? When does the
user unlock or favor it?]

- **Primary effect:** [EFFECT]
- **Unlock condition:** [CONDITION]
- **Example instances:** [EXAMPLE_A], [EXAMPLE_B]

### [CATEGORY_2_NAME]

[Description of this category.]

- **Primary effect:** [EFFECT]
- **Unlock condition:** [CONDITION]
- **Example instances:** [EXAMPLE_A], [EXAMPLE_B]

### [CATEGORY_3_NAME]

[Description of this category.]

- **Primary effect:** [EFFECT]
- **Unlock condition:** [CONDITION]
- **Example instances:** [EXAMPLE_A], [EXAMPLE_B]

---

## Meta / Core Hook

The meta layer is what keeps users returning across multiple sessions. It sits above the
core loop and provides longer-term goals.

**The central hook:** [Describe in 2-3 sentences what makes the long-term progression
compelling. What is the user always working toward? What changes between sessions?]

**Retention drivers:**

- **Short-term (within session):** [What keeps the user engaged for 5-15 minutes?]
- **Medium-term (across sessions):** [What gives the user a goal to return for?]
- **Long-term (weeks/months):** [What provides value to dedicated long-term users?]

---

## Monetization Approach

[PROJECT_NAME] is monetized via [MONETIZATION_MODEL, e.g. "premium one-time purchase",
"in-app purchases only", "subscription", "ads with optional IAP"].

**Guiding principles:**

- [PRINCIPLE_1, e.g. "No purchase should be required to complete the core experience."]
- [PRINCIPLE_2, e.g. "Purchasable items must provide convenience, not unfair advantage."]
- [PRINCIPLE_3, e.g. "Pricing must be transparent with no loot-box mechanics."]

**Purchasable items (high level):**

| Item | Category | Effect |
|------|----------|--------|
| [ITEM_1] | [convenience / cosmetic / expansion] | [Effect description] |
| [ITEM_2] | [convenience / cosmetic / expansion] | [Effect description] |
| [ITEM_3] | [convenience / cosmetic / expansion] | [Effect description] |

Detailed monetization design is documented in `ADDITIONAL.md`.

---

## Progression Pacing

The intended pacing is designed around the following benchmarks:

| Session | Expected State |
|---------|----------------|
| First session | [What should a new user experience and accomplish?] |
| After [TIME_1] of total play | [What should the user have unlocked or achieved?] |
| After [TIME_2] of total play | [What major system or milestone should be accessible?] |
| After [TIME_3] of total play | [What represents the mid-game state?] |
| Long-term / endgame | [What does the late-game experience look like?] |

Detailed pacing data (costs, rates, scaling formulae) are documented in `PRD.md` and
`ADDITIONAL.md`.
