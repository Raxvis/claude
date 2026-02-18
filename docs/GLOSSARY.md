<!-- TEMPLATE INSTRUCTIONS
  FILE: GLOSSARY.md
  PURPOSE: Provides canonical, unambiguous definitions for every domain-specific term
  used across the project's documents and codebase. When any document uses a term that
  might be misunderstood or that has a project-specific meaning, that term belongs here.
  This document is the single source of truth for terminology. If two documents use the
  same word differently, the definition here wins and the documents must be updated.

  HOW TO CUSTOMIZE:
  - Replace all [TERM_NAME] and [PLACEHOLDER] tokens with real terms and definitions.
  - Organize terms into the categories below, adding new categories if needed.
  - Write definitions in the present tense, as facts: "[TERM] is..." not "[TERM] will be..."
  - Cross-reference related terms using "See also: [OTHER_TERM]".
  - If a term is used in the codebase with a specific identifier (e.g. an interface name
    or a store field name), note the code identifier alongside the human-readable definition.
  - Keep definitions concise — one to three sentences. Detail belongs in ADDITIONAL.md.
  - Remove placeholder entries that you have not yet replaced; do not leave unfilled
    [TERM_NAME] entries in the final document.
-->

# [PROJECT_NAME] — Glossary

All terms are listed alphabetically within each category. Terms shown in **bold** within
a definition are themselves defined in this glossary.

---

## Core Concepts

**[TERM_NAME]**
[Define the most fundamental concept in the project. What is the primary object, action,
or system the user interacts with? This definition should be understandable to someone
with no prior context.] See also: [RELATED_TERM].

**[TERM_NAME]**
[Define the core loop or primary interaction cycle. Describe what it means without
assuming the reader has read any other document.]

**[TERM_NAME]**
[Define a key state or condition the system can be in, e.g. "the state in which the
application is running without user interaction". Note the code identifier if applicable:
`[CODE_IDENTIFIER]`.]

**[TERM_NAME]**
[Define a key unit of measurement or progress, e.g. "the smallest indivisible unit of
player-controlled content". Note: in the codebase this is represented by the
`[CodeInterfaceName]` interface.]

**[TERM_NAME]**
[Define another foundational concept. Keep it to two or three sentences.]

---

## Resources and Economy

**[TERM_NAME]**
[Define the primary currency or resource. Include its symbol or abbreviation if it has
one, and the unit of measurement, e.g. "measured in [UNIT] per [TIME_UNIT]".]

**[TERM_NAME]**
[Define a secondary currency or resource. Note whether it persists through reset events
and what it is primarily spent on.]

**[TERM_NAME]**
[Define a premium or special-purpose currency. Note whether it is directly purchasable
and whether it persists through resets.]

**[TERM_NAME]**
[Define the production rate concept. Clarify the time basis, e.g. "always expressed in
[RESOURCE] per second regardless of the internal tick interval".]

**[TERM_NAME]**
[Define the concept of a rate multiplier or bonus, e.g. "a dimensionless scalar applied
to a base production rate. Multipliers from different sources are combined
[additively / multiplicatively]".]

---

## Domain-Specific Terms

**[TERM_NAME]**
[Define the primary domain entity — the central object that users create, manage, or
interact with throughout the experience.]

**[TERM_NAME]**
[Define a subtype or variant of the primary domain entity. Distinguish it clearly from
related terms.]

**[TERM_NAME]**
[Define a structural or organizational unit, e.g. a container, group, or hierarchy level
that organizes domain entities.]

**[TERM_NAME]**
[Define an action-specific term, e.g. an operation the user performs on a domain entity.]

**[TERM_NAME]**
[Define a state that a domain entity can be in, e.g. "active", "locked", "maxed".]

---

## Progression and Unlocks

**[TERM_NAME]**
[Define the primary unit of progression — what advances as the user plays, e.g. a level,
a count, a score. Note how it is displayed in the UI.]

**[TERM_NAME]**
[Define the concept of unlocking, i.e. the mechanism by which new content becomes
available. Note what triggers unlocks in this project.]

**[TERM_NAME]**
[Define the upgrade concept — how an existing entity increases in power or capability.
Note the cost model (e.g. exponential scaling).]

**[TERM_NAME]**
[Define the reset or rebirth mechanic, if applicable. Explain what the user gains and
what is lost when a reset is performed. If there is no reset mechanic, remove this entry.]

**[TERM_NAME]**
[Define the concept of a milestone — a named, discrete point in the progression arc that
represents a significant achievement or transition.]

---

## Technical Terms

**[TERM_NAME]**
[Define a technical concept that appears in the codebase and documents but might be
unfamiliar to a new contributor, e.g. a data representation pattern, a serialization
approach, or a precision handling technique. Reference the relevant source file.]

**[TERM_NAME]**
[Define the tick — the discrete unit of time used by the main update loop. State the
tick interval and note that it is defined in `[CODE_FILE_PATH]`.]

**[TERM_NAME]**
[Define the save format or persistence concept. Note the storage key and version field
convention.]

**[TERM_NAME]**
[Define the state store concept as used in this project. Reference the file where the
store is defined.]

**[TERM_NAME]**
[Define a notable algorithmic or mathematical concept used in the project, e.g. a
scaling formula, a capping approach, or a normalization technique.]

---

## UI Terms

**[TERM_NAME]**
[Define the primary screen or view the user sees during normal use.]

**[TERM_NAME]**
[Define a key UI element or component, e.g. the main content list, the resource display,
or the primary action button.]

**[TERM_NAME]**
[Define a UI state, e.g. the state of a button when the user cannot afford the action it
represents.]

**[TERM_NAME]**
[Define a modal or overlay concept used in the UI, e.g. the dialog that appears when
offline progress is applied.]

**[TERM_NAME]**
[Define a layout term, e.g. the direction in which the primary list is ordered visually.]

---

## Abbreviations

| Abbreviation | Meaning |
|-------------|---------|
| [ABBR_1] | [FULL_TERM_1] |
| [ABBR_2] | [FULL_TERM_2] |
| [ABBR_3] | [FULL_TERM_3] |
| [ABBR_4] | [FULL_TERM_4] |
| [ABBR_5] | [FULL_TERM_5] |
| IAP | In-App Purchase |
| MVP | Minimum Viable Product |
| PRD | Product Requirements Document |
| KPI | Key Performance Indicator |
| ARPU | Average Revenue Per User |
| ARPPU | Average Revenue Per Paying User |
