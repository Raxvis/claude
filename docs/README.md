<!-- TEMPLATE INSTRUCTIONS
  FILE: README.md
  PURPOSE: This file serves as the master navigation index for all project documentation.
  It provides a single entry point so that any contributor (human or AI agent) can quickly
  locate the relevant document for a given concern.

  HOW TO CUSTOMIZE:
  - Replace [PROJECT_NAME] with the name of your project throughout.
  - Add, remove, or re-categorize documents to match the actual files present in your project.
  - Update the brief descriptions so they reflect the real content of each document.
  - Remove any categories or entries that are not applicable to your project.
  - If you add new documentation files, register them here immediately.
-->

# [PROJECT_NAME] — Documentation Index

This file is the entry point for all project documentation. If you are looking for a
specific piece of information, start here to find the correct document.

---

## Design Documents

These documents describe what the project is, why it exists, and how it is designed.

| File | Description |
|------|-------------|
| `CONCEPT.md` | High-level project vision, core loop, and design pillars. Start here for a first-principles understanding of the project. |
| `PRD.md` | Product Requirements Document. Defines features, user stories, acceptance criteria, success metrics, and constraints. |
| `ADDITIONAL.md` | Extended design details that expand on the PRD. Covers systems, rules, and specifications too detailed for the PRD itself. |
| `GLOSSARY.md` | Canonical definitions for all domain-specific terms used across documents. Resolve any naming ambiguities here. |
| `DESIGN_RATIONALE.md` | Decision log recording significant design choices, the reasoning behind them, and the trade-offs accepted. |

---

## Technical Documents

These documents describe how the project is built and the conventions that govern the codebase.

| File | Description |
|------|-------------|
| `CODE_PATTERNS.md` | Coding conventions, naming rules, module structure, component lifecycle, and state management patterns. |
| `FILE_CONVENTIONS.md` | Rules governing where each type of file and document belongs in the repository. Read before creating any new file. |
| `ERROR_HANDLING.md` | Guidelines for handling errors across all error categories. Defines principles, patterns, and user-facing message standards. |
| `TEST_FRAMEWORK.md` | Testing strategy, test runner setup, file conventions, coverage requirements, and best practices. |

---

## Project Tracking

These documents track the live state of the project: bugs, progress, and milestones.

| File | Description |
|------|-------------|
| `BUGS.md` | Active bug tracker. Documents known issues, reproduction steps, and resolution status. |
| `CHANGELOG.md` | Chronological log of notable changes across releases and milestones. Maintained by the release agent. |
| `ASSETS.md` | Registry of all project assets (images, fonts, etc.) with status and source information. |
| `MVP_LAUNCH.md` | Checklist and criteria for the initial public release. |
| `STANDUP.md` | Running log of progress updates, blockers, and decisions from work sessions. |
| `MILESTONE_VALIDATION.md` | Template for milestone acceptance records. Copy to `docs/milestones/` for each milestone. |

---

## Templates

Reusable document templates to be copied and filled in when documenting new modules,
systems, data schemas, UI screens, or task breakdowns.

| File | Description |
|------|-------------|
| `ARCH_MODULE.md` | Template for documenting a single code module (purpose, interface, dependencies, error handling). |
| `ARCH_SYSTEM.md` | Template for documenting a high-level system composed of multiple modules. |
| `ARCH_DATA_SCHEMA.md` | Template for documenting a data schema or save format. |
| `UI_SPEC.md` | Template for specifying a UI screen or component (layout, states, interactions, accessibility). |
| `MILESTONE_TASKS.md` | Template for breaking a milestone into concrete, actionable tasks with acceptance criteria. Copy to `docs/milestones/` for each milestone. |
| `MILESTONE_COMPLETION.md` | Template for milestone completion reports. Copy to `docs/milestones/` after a milestone is validated. |

---

## How to Use This Documentation

1. **Starting a new feature?** Read `PRD.md` for requirements and `CODE_PATTERNS.md` for conventions.
2. **Confused by a term?** Check `GLOSSARY.md` first.
3. **Creating a new file?** Read `FILE_CONVENTIONS.md` before deciding where to put it.
4. **Documenting a design decision?** Add an entry to `DESIGN_RATIONALE.md`.
5. **Found a bug?** Log it in `BUGS.md`.
6. **Completing a milestone?** Fill in `MILESTONE_VALIDATION.md`.

---

_Last updated: [YYYY-MM-DD]_
