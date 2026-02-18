<!-- TEMPLATE INSTRUCTIONS
  FILE: ADDITIONAL.md
  PURPOSE: This document contains extended design detail that is true to the project's
  vision but too granular or voluminous to live comfortably in PRD.md. It covers advanced
  systems, the nuances of individual mechanics, detailed pacing targets, monetization
  specifics, and post-launch plans. The PRD says "what must be true"; this document says
  "here is exactly how it works in detail".

  HOW TO CUSTOMIZE:
  - Replace all [PLACEHOLDER] tokens with real project terms.
  - Delete any section that does not apply to your project. For example, if your project
    has no passive/idle dimension, delete "Idle/Offline Play" entirely.
  - If a section grows very large, consider splitting it into its own file and linking to
    it from here.
  - This document should be kept in sync with PRD.md. If a design decision changes,
    update both files.
-->

# [PROJECT_NAME] — Extended Design Details

---

## Progression / Reset System

> **NOTE TO AUTHOR:** This section describes a meta-progression reset mechanic (sometimes
> called "prestige" or "rebirth"). Delete it entirely if your project has no such mechanic.

[PROJECT_NAME] includes a voluntary [RESET_MECHANIC_NAME] system. When triggered, the
user's current [PROGRESSION_UNIT] is reset in exchange for [RESET_REWARD], which provides
permanent bonuses to future runs.

**Trigger condition:** The user may initiate [RESET_MECHANIC_NAME] at any time after
reaching [MINIMUM_CONDITION_TO_UNLOCK_RESET].

**What resets:**

- [ITEM_THAT_RESETS_1]
- [ITEM_THAT_RESETS_2]
- [ITEM_THAT_RESETS_3]

**What persists:**

- [ITEM_THAT_PERSISTS_1, e.g. "Purchased permanent upgrades"]
- [ITEM_THAT_PERSISTS_2, e.g. "Lifetime statistics"]
- [ITEM_THAT_PERSISTS_3, e.g. "Cosmetic unlocks"]

**Reward scaling formula:**

```
[RESET_REWARD] = floor(sqrt([LIFETIME_METRIC] / [THRESHOLD_CONSTANT]))
```

**Balance targets:**

| [RESET_COUNT] | Expected [LIFETIME_METRIC] at reset | [RESET_REWARD] granted |
|---------------|--------------------------------------|------------------------|
| 1st | [VALUE] | [VALUE] |
| 2nd | [VALUE] | [VALUE] |
| 3rd | [VALUE] | [VALUE] |

---

## Layout and Structure

[PROJECT_NAME]'s visual layout is organized as [describe the primary layout metaphor,
e.g. "a vertical list", "a grid", "a branching tree"].

**Primary dimensions:**

- [DIMENSION_1]: [Description and constraints, e.g. "Maximum of [N] visible at once"]
- [DIMENSION_2]: [Description and constraints]
- [DIMENSION_3]: [Description and constraints]

**Visual hierarchy rules:**

- [RULE_1, e.g. "The most recently added item appears at position [TOP/BOTTOM]."]
- [RULE_2, e.g. "Items are grouped by [CATEGORY]."]
- [RULE_3, e.g. "Locked items are shown but visually distinct from unlocked items."]

---

## [DOMAIN_ENTITY] Types and Categories

[DOMAIN_ENTITY] instances fall into [NUMBER] categories. Each category has distinct
production characteristics, unlock conditions, and visual treatments.

### [CATEGORY_1]

| Property | Value |
|----------|-------|
| Base [RESOURCE_TYPE] rate | [VALUE] per [TIME_UNIT] |
| Base cost | [VALUE] |
| Cost scaling factor | [FORMULA] |
| Unlock condition | [CONDITION] |
| Upgrade cap | [CAP or "None"] |
| Visual indicator | [DESCRIPTION] |

[Narrative description of this category's design intent and role in the economy.]

### [CATEGORY_2]

| Property | Value |
|----------|-------|
| Base [RESOURCE_TYPE] rate | [VALUE] per [TIME_UNIT] |
| Base cost | [VALUE] |
| Cost scaling factor | [FORMULA] |
| Unlock condition | [CONDITION] |
| Upgrade cap | [CAP or "None"] |
| Visual indicator | [DESCRIPTION] |

[Narrative description.]

### [CATEGORY_3]

| Property | Value |
|----------|-------|
| Base [RESOURCE_TYPE] rate | [VALUE] per [TIME_UNIT] |
| Base cost | [VALUE] |
| Cost scaling factor | [FORMULA] |
| Unlock condition | [CONDITION] |
| Upgrade cap | [CAP or "None"] |
| Visual indicator | [DESCRIPTION] |

[Narrative description.]

---

## Unlock System

New [DOMAIN_ENTITY] types and features are unlocked progressively to avoid overwhelming
new users and to maintain a sense of discovery.

**Unlock mechanism:** [Describe how unlocks are triggered, e.g. "by reaching a
[PROGRESSION_UNIT] count threshold", "by spending [RESOURCE_TYPE]", "by completing a
prerequisite action".]

**Unlock sequence:**

| Unlock Order | Item Unlocked | Condition |
|-------------|---------------|-----------|
| 1 | [ITEM] | [CONDITION, e.g. "Available from the start"] |
| 2 | [ITEM] | [CONDITION] |
| 3 | [ITEM] | [CONDITION] |
| 4 | [ITEM] | [CONDITION] |
| 5 | [ITEM] | [CONDITION] |

**UI treatment for locked items:**

- Locked items [are shown / are hidden] until [CONDITION].
- When shown but locked, they display [WHAT_IS_VISIBLE, e.g. "a placeholder image and
  the unlock condition"].
- When unlocked, they [TRANSITION_DESCRIPTION].

---

## Upgrade and Evolution

[DOMAIN_ENTITY] instances can be upgraded over time. Upgrades increase [PRIMARY_EFFECT]
and may unlock new [SECONDARY_EFFECT].

**Upgrade model:**

- Each [DOMAIN_ENTITY] has [NUMBER_OR_UNLIMITED] upgrade levels.
- Upgrade cost formula: `[BASE_COST] * [GROWTH_RATE] ^ [CURRENT_LEVEL]`
- Growth rate range: [MIN_RATE] to [MAX_RATE] (higher = steeper cost curve)

**Upgrade effects:**

| Upgrade Level | [EFFECT_1] | [EFFECT_2] | Notes |
|--------------|-----------|-----------|-------|
| 1 (base) | [VALUE] | [VALUE] | — |
| 2 | [VALUE] | [VALUE] | [NOTE] |
| 3 | [VALUE] | [VALUE] | [NOTE] |
| [MAX] | [VALUE] | [VALUE] | [MAX_UNLOCK_DESCRIPTION] |

---

## [CORE_MECHANIC] System

[CORE_MECHANIC] is the primary driver of [RESOURCE_TYPE] generation. It is calculated
once per [TICK_INTERVAL] and applied to the user's total.

**Calculation:**

```
[RESOURCE_TYPE] per tick =
  sum over all active [DOMAIN_ENTITY]:
    [DOMAIN_ENTITY].baseRate
    * [MULTIPLIER_1]
    * [MULTIPLIER_2]
    * [GLOBAL_MODIFIER]
```

**Multiplier sources:**

- [MULTIPLIER_1]: [What grants this multiplier and by how much]
- [MULTIPLIER_2]: [What grants this multiplier and by how much]
- [GLOBAL_MODIFIER]: [What grants this modifier]

**Tick interval:** [TICK_INTERVAL, e.g. "500ms"] — see `CODE_PATTERNS.md` for
implementation details.

---

## Active Play Mechanics

While [PROJECT_NAME] functions as a passive experience, active play provides bonus
[RESOURCE_TYPE] or accelerates progress.

| Mechanic | Description | Reward |
|----------|-------------|--------|
| [ACTIVE_MECHANIC_1] | [How the user performs it] | [What they receive] |
| [ACTIVE_MECHANIC_2] | [How the user performs it] | [What they receive] |
| [ACTIVE_MECHANIC_3] | [How the user performs it] | [What they receive] |

**Cooldowns and limits:** [Describe any rate-limiting on active mechanics to prevent
trivial exploit of active bonuses.]

---

## Idle / Offline Play

> **NOTE TO AUTHOR:** Delete this section if the project has no offline accumulation.

When the user is not in the application, [PROJECT_NAME] simulates progress at the
[RESOURCE_TYPE] rate applicable at the time the application was last active.

**Cap:** Offline accumulation is capped at [TIME_CAP] to prevent save-scumming and
device-clock exploits.

**Calculation method:** Deterministic. Given the same save state and the same elapsed
seconds, the result is always identical. No randomness is introduced.

**Return experience:**
1. Upon reopening, the application calculates [EARNINGS] = [RATE] * [CAPPED_ELAPSED_SECONDS].
2. The user is shown a [RETURN_MODAL_DESCRIPTION] summarizing what was earned.
3. The earned [RESOURCE_TYPE] is credited to the user's total.

**Clock manipulation handling:**
- If `now < lastSaveTime`, elapsed time is treated as 0 (negative time is ignored).
- If `now - lastSaveTime > [HARD_CAP]`, elapsed is clamped to [HARD_CAP].

---

## Currencies

[PROJECT_NAME] uses [NUMBER] distinct currencies:

### [CURRENCY_1_NAME]

- **Type:** [Primary / Secondary / Premium / Prestige]
- **Earned by:** [HOW_EARNED]
- **Spent on:** [WHAT_IT_BUYS]
- **Can be purchased?** [Yes / No]
- **Persists through [RESET_MECHANIC_NAME]?** [Yes / No]
- **Display format:** [e.g. "1.5T", "$1,500", "1500"]

### [CURRENCY_2_NAME]

- **Type:** [Primary / Secondary / Premium / Prestige]
- **Earned by:** [HOW_EARNED]
- **Spent on:** [WHAT_IT_BUYS]
- **Can be purchased?** [Yes / No]
- **Persists through [RESET_MECHANIC_NAME]?** [Yes / No]
- **Display format:** [FORMAT]

### [CURRENCY_3_NAME] (if applicable)

- **Type:** [Primary / Secondary / Premium / Prestige]
- **Earned by:** [HOW_EARNED]
- **Spent on:** [WHAT_IT_BUYS]
- **Can be purchased?** [Yes / No]
- **Persists through [RESET_MECHANIC_NAME]?** [Yes / No]
- **Display format:** [FORMAT]

---

## Placement and Arrangement

[Describe any spatial or slot-based arrangement rules for [DOMAIN_ENTITY] instances.
If there are no placement mechanics, delete this section.]

- [DOMAIN_ENTITY] instances are placed in [SLOT/GRID/LIST] structures.
- Maximum capacity per [CONTAINER_UNIT]: [NUMBER_OR_FORMULA]
- Placement order: [DESCRIPTION, e.g. "User-chosen", "Automatic by unlock order"]
- Reordering: [Is reordering allowed? How?]

---

## Monetization Details

[PROJECT_NAME] is free to download and uses [MONETIZATION_MODEL].

### [PURCHASABLE_ITEM_CATEGORY_1]

| Item | Effect | Price Tier |
|------|--------|-----------|
| [ITEM_1] | [EFFECT] | [TIER, e.g. "$0.99"] |
| [ITEM_2] | [EFFECT] | [TIER] |
| [ITEM_3] | [EFFECT] | [TIER] |

### [PURCHASABLE_ITEM_CATEGORY_2]

| Item | Effect | Price Tier |
|------|--------|-----------|
| [ITEM_1] | [EFFECT] | [TIER] |
| [ITEM_2] | [EFFECT] | [TIER] |

**Restore purchases:** The application must support purchase restoration on all platforms
that require it. Restored purchases are processed identically to new purchases.

**Receipt validation:** [Describe the receipt validation approach: client-side, server-side,
or deferred to post-launch.]

---

## Progression Pacing

The following table describes the intended pacing arc. All values are targets; actual
playtest data may cause adjustments.

| Milestone | [PROGRESSION_UNIT] Count | Approximate Play Time | [RESOURCE_TYPE] Rate |
|-----------|--------------------------|----------------------|----------------------|
| [MILESTONE_1] | [VALUE] | [TIME] | [RATE] |
| [MILESTONE_2] | [VALUE] | [TIME] | [RATE] |
| [MILESTONE_3] | [VALUE] | [TIME] | [RATE] |
| [MILESTONE_4] | [VALUE] | [TIME] | [RATE] |
| [MILESTONE_5] | [VALUE] | [TIME] | [RATE] |

**Pacing principles:**

- Early game ([EARLY_RANGE]): [DESCRIPTION, e.g. "Rapid unlock cadence. New items every 1-3 minutes."]
- Mid game ([MID_RANGE]): [DESCRIPTION, e.g. "Deliberate decisions. Upgrades take meaningful time."]
- Late game ([LATE_RANGE]): [DESCRIPTION, e.g. "Optimization focus. Prestige cycle becomes attractive."]

---

## Events and Seasons (Post-Launch)

> **NOTE TO AUTHOR:** This section is for planned post-launch live events. Delete if not
> applicable or move it to the post-launch roadmap section of PRD.md.

Timed events will be introduced post-launch to drive re-engagement.

**Event format:** [Describe the general structure of events, e.g. "Limited-time challenges
with exclusive cosmetic rewards".]

**Cadence:** [Planned frequency, e.g. "Monthly" or "Seasonal".]

**Event types under consideration:**

- [EVENT_TYPE_1]: [Brief description]
- [EVENT_TYPE_2]: [Brief description]
- [EVENT_TYPE_3]: [Brief description]

---

## Social Features

> **NOTE TO AUTHOR:** Delete this section if no social features are planned.

Post-launch social features under consideration:

- **[SOCIAL_FEATURE_1]:** [Brief description and benefit to users]
- **[SOCIAL_FEATURE_2]:** [Brief description and benefit to users]
- **[SOCIAL_FEATURE_3]:** [Brief description and benefit to users]

---

## Media and Visual Style

### Visual Style

[PROJECT_NAME] uses a [VISUAL_STYLE_DESCRIPTION, e.g. "dark, atmospheric color palette
with high-contrast accent colors"] aesthetic. Design references: [REFERENCE_1], [REFERENCE_2].

**Color palette:** Defined in `[THEME_FILE_PATH]`. Use the constants defined there; do
not use inline hex values.

**Asset specifications:**

| Asset Type | Format | Target Resolution | Notes |
|-----------|--------|------------------|-------|
| [ASSET_TYPE_1] | [FORMAT] | [RESOLUTION] | [NOTES] |
| [ASSET_TYPE_2] | [FORMAT] | [RESOLUTION] | [NOTES] |
| [ASSET_TYPE_3] | [FORMAT] | [RESOLUTION] | [NOTES] |
