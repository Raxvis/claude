<!-- TEMPLATE INSTRUCTIONS
  FILE: FILE_CONVENTIONS.md
  PURPOSE: This document defines the exact location and naming rules for every category
  of file in the project. It exists to ensure that any contributor — human or AI agent —
  places new files in predictable, discoverable locations and names them consistently.
  Without this document, documentation and generated files accumulate in random locations
  and become impossible to navigate.

  HOW TO CUSTOMIZE:
  - Replace all [PLACEHOLDER] tokens with real project directory and file names.
  - Update the directory tree diagram to reflect the actual structure of your project's
    `docs/` directory.
  - Adjust the naming conventions to match the conventions already established in your
    project.
  - Add or remove document type sections to match the kinds of artifacts your project
    actually produces.
  - The "Agent Responsibilities" subsections are specifically for AI agents working on
    the project. Update them to reflect the actual workflow your project uses.
-->

# [PROJECT_NAME] — File and Directory Placement Rules

This document governs where every file in the `docs/` directory belongs. Read this
document before creating any new file. When in doubt, place files here rather than
at the repository root.

---

## Documentation Structure

```
docs/
  README.md                      # Documentation index (this directory)
  CONCEPT.md                     # Project vision
  PRD.md                         # Product requirements
  ADDITIONAL.md                  # Extended design detail
  GLOSSARY.md                    # Term definitions
  DESIGN_RATIONALE.md            # Decision log
  CODE_PATTERNS.md               # Coding conventions
  FILE_CONVENTIONS.md            # This document
  ERROR_HANDLING.md              # Error handling guidelines
  TEST_FRAMEWORK.md              # Testing strategy
  BUGS.md                        # Active bug tracker
  CHANGELOG.md                   # Release history
  ASSETS.md                      # Asset registry
  MVP_LAUNCH.md                  # Launch checklist
  STANDUP.md                     # Session progress log

  milestones/
    [MILESTONE_NAME]_TASKS.md    # Task breakdown per milestone
    [MILESTONE_NAME]_VALIDATION.md # Acceptance record per milestone

  architecture/
    [MODULE_NAME]_MODULE.md      # Per-module architecture docs
    [SYSTEM_NAME]_SYSTEM.md      # Per-system architecture docs
    [SCHEMA_NAME]_SCHEMA.md      # Data schema docs

  ui-specs/
    [SCREEN_NAME]_SCREEN.md      # Per-screen UI specification
    [COMPONENT_NAME]_COMPONENT.md # Per-component UI specification
```

> **Note:** The base template stores document templates in the `docs/` root using generic names (e.g., `ARCH_MODULE.md`, `UI_SPEC.md`, `MILESTONE_TASKS.md`). The subdirectory structure shown above (`milestones/`, `architecture/`, `ui-specs/`) is created when the first instance of each document type is produced. Instance files use the naming patterns shown in the diagram (e.g., `[MODULE_NAME]_MODULE.md`).

---

## File Naming and Placement Rules

### Core Design and Technical Documents

These files live directly in `docs/` and must not be moved or renamed.

| File | Contents |
|------|----------|
| `README.md` | Documentation index — lists all other docs with descriptions |
| `CONCEPT.md` | Project vision, core loop, design pillars |
| `PRD.md` | Product requirements, user stories, acceptance criteria |
| `ADDITIONAL.md` | Extended design details |
| `GLOSSARY.md` | Canonical term definitions |
| `DESIGN_RATIONALE.md` | Decision log |
| `CODE_PATTERNS.md` | Coding conventions |
| `FILE_CONVENTIONS.md` | File placement rules (this document) |
| `ERROR_HANDLING.md` | Error handling guidelines |
| `TEST_FRAMEWORK.md` | Testing strategy |
| `BUGS.md` | Active bug log |
| `CHANGELOG.md` | Chronological change log |
| `ASSETS.md` | Asset registry |
| `MVP_LAUNCH.md` | Launch readiness checklist |
| `STANDUP.md` | Running session log |

---

### Milestone Reports

**Location:** `docs/milestones/`

**Naming pattern:** `[MILESTONE_NAME]_VALIDATION.md`

**Format:**
- `[MILESTONE_NAME]` is the identifier used for that milestone in `PRD.md` (e.g. `M1`, `ALPHA`).
- Use `UPPER_SNAKE_CASE` for the milestone identifier.
- The suffix `_VALIDATION.md` is fixed and must not vary.

**Examples:**
- `docs/milestones/M1_VALIDATION.md`
- `docs/milestones/ALPHA_VALIDATION.md`

**Agent responsibilities:**
- When completing a milestone, create the validation file at this path.
- Do not create validation files at the repository root or in any other `docs/` subdirectory.

---

### Task-Related Documents

Task documents live in `docs/milestones/` and follow fixed naming suffixes.

#### Task Breakdowns

**Naming:** `[MILESTONE_NAME]_TASKS.md`

Use this file to list all tasks for a milestone before work begins.

#### Completion Reports

**Naming:** `[MILESTONE_NAME]_COMPLETION.md`

Created after a milestone is fully done. Summarizes what was built, what was deferred,
and lessons learned.

#### Code Reviews

**Naming:** `[FEATURE_OR_PR_NAME]_REVIEW.md`

Records the findings of a code review. [FEATURE_OR_PR_NAME] matches the feature branch
name or PR identifier.

#### Implementation Guides

**Naming:** `[FEATURE_NAME]_IMPL.md`

Step-by-step implementation notes for a specific feature, written before or during
implementation. Use these to capture decisions made during a work session.

#### Checklists

**Naming:** `[SCOPE]_CHECKLIST.md`

A checklist of verifiable items for a specific scope (e.g. `LAUNCH_CHECKLIST.md`,
`[MILESTONE]_CHECKLIST.md`).

#### Validations

**Naming:** `[SCOPE]_VALIDATION.md`

Records acceptance of a scope (milestone, feature, or release) against stated criteria.

---

### Architecture Specifications

**Location:** `docs/architecture/`

**Naming patterns:**

| Document Type | Naming Convention | Example |
|--------------|-------------------|---------|
| Module spec | `[MODULE_NAME]_MODULE.md` | `[EXAMPLE_MODULE]_MODULE.md` |
| System spec | `[SYSTEM_NAME]_SYSTEM.md` | `[EXAMPLE_SYSTEM]_SYSTEM.md` |
| Data schema | `[SCHEMA_NAME]_SCHEMA.md` | `[EXAMPLE_SCHEMA]_SCHEMA.md` |

**Agent responsibilities:**
- When asked to document a module or system, create the file at `docs/architecture/`.
- Use the corresponding template from `docs/ARCH_MODULE.md`, `docs/ARCH_SYSTEM.md`, or
  `docs/ARCH_DATA_SCHEMA.md`.
- Register the new file in `docs/README.md`.

---

### UI Specifications

**Location:** `docs/ui-specs/`

**Naming patterns:**

| Document Type | Naming Convention | Example |
|--------------|-------------------|---------|
| Screen spec | `[SCREEN_NAME]_SCREEN.md` | `[EXAMPLE_SCREEN]_SCREEN.md` |
| Component spec | `[COMPONENT_NAME]_COMPONENT.md` | `[EXAMPLE_COMPONENT]_COMPONENT.md` |

**Agent responsibilities:**
- When asked to specify a screen or component, create the file at `docs/ui-specs/`.
- Use the `docs/UI_SPEC.md` template.
- Register the new file in `docs/README.md`.

---

## Agent Responsibilities Summary

| Situation | Action Required |
|-----------|----------------|
| Completing a milestone | Create `docs/milestones/[MILESTONE_NAME]_VALIDATION.md` |
| Documenting a module | Create `docs/architecture/[MODULE_NAME]_MODULE.md` |
| Documenting a system | Create `docs/architecture/[SYSTEM_NAME]_SYSTEM.md` |
| Documenting a schema | Create `docs/architecture/[SCHEMA_NAME]_SCHEMA.md` |
| Specifying a UI screen | Create `docs/ui-specs/[SCREEN_NAME]_SCREEN.md` |
| Planning a milestone | Create `docs/milestones/[MILESTONE_NAME]_TASKS.md` |
| Recording a decision | Add an entry to `docs/DESIGN_RATIONALE.md` |
| Logging a bug | Add an entry to `docs/BUGS.md` |
| Creating any new doc | Register it in `docs/README.md` |

---

## Anti-Patterns

The following behaviors violate these conventions. Do not do them:

- **Creating files at the repository root.** Documentation does not belong at `/`.
  Exception: `README.md`, `CHANGELOG.md`, and tool configuration files that require
  root placement by convention.
- **Creating new subdirectories inside `docs/` without updating this file.** Any new
  subdirectory must be added to the tree diagram above and documented.
- **Using free-form naming.** All document names must follow the naming patterns in this
  file. Do not invent new suffixes or structures.
- **Duplicating documents.** Never create a second file for a concern that already has a
  canonical home. Update the existing file instead.
- **Leaving documents unregistered.** Every document created must have an entry in
  `docs/README.md`.

---

## Quick Reference

| Document type | Location | Naming |
|--------------|----------|--------|
| Core design/tech docs | `docs/` | `UPPER_SNAKE_CASE.md` |
| Milestone tasks | `docs/milestones/` | `[MILESTONE]_TASKS.md` |
| Milestone validation | `docs/milestones/` | `[MILESTONE]_VALIDATION.md` |
| Completion reports | `docs/milestones/` | `[MILESTONE]_COMPLETION.md` |
| Code reviews | `docs/milestones/` | `[FEATURE]_REVIEW.md` |
| Implementation guides | `docs/milestones/` | `[FEATURE]_IMPL.md` |
| Checklists | `docs/milestones/` | `[SCOPE]_CHECKLIST.md` |
| Module architecture | `docs/architecture/` | `[MODULE]_MODULE.md` |
| System architecture | `docs/architecture/` | `[SYSTEM]_SYSTEM.md` |
| Data schemas | `docs/architecture/` | `[SCHEMA]_SCHEMA.md` |
| Screen specs | `docs/ui-specs/` | `[SCREEN]_SCREEN.md` |
| Component specs | `docs/ui-specs/` | `[COMPONENT]_COMPONENT.md` |

---

## Rationale

These conventions exist for three reasons:

1. **Discoverability.** When files have predictable names and locations, any contributor
   can find what they need without asking. The directory tree is a map.

2. **Agent reliability.** AI agents working on this project must produce outputs in
   deterministic, predictable locations. Ambiguous conventions cause agents to create
   files in wrong places, requiring manual cleanup.

3. **Reviewability.** Consistent naming makes it possible to review the completeness of
   documentation at a glance: if a milestone exists in `PRD.md` but has no corresponding
   `_TASKS.md` and `_VALIDATION.md`, it is immediately visible.

---

_Last updated: [YYYY-MM-DD]_
