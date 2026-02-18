# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repository Is

This is a **multi-agent AI-assisted development workflow template**. It contains no source code — only markdown template files with `[PLACEHOLDER]` tokens that are replaced when adapting the template to a new project. The template establishes agent roles, documentation structure, and development conventions for AI-assisted software projects.

## Directory Structure

- **`root/`** — Files copied to a target project's root (CLAUDE.md template, config templates)
- **`agents/`** — 16 agent role definitions plus a master `README.md` (product, architect, UI, coder, reviewer, tester, debugger, refactor, docs-writer, ux-critic, security, performance, release, asset-gen, validator, bug-gatherer). Each file defines one agent's purpose, authority, inputs, outputs, and decision log
- **`docs/`** — Shared reference document templates (PRD, architecture, glossary, UI specs, milestone tracking, etc.)

## Placeholder Convention

All project-specific content uses `[UPPER_SNAKE_CASE]` tokens in square brackets. Categories: Identity (`[PROJECT_NAME]`, `[PROJECT_TYPE]`), Tech (`[FRAMEWORK]`, `[LANGUAGE]`), Commands (`[DEV_SERVER_CMD]`, `[TEST_CMD]`), Domain (`[DOMAIN_ENTITY]`, `[CORE_MECHANIC]`), Platform (`[TARGET_PLATFORMS]`), Agents (`[AI_MODEL]`).

When editing templates, preserve placeholder tokens — do not replace them with concrete values unless adapting the template for a specific project.

## Agent System Architecture

16 agent roles form a pipeline: **Product** (requirements) → **Architecture** + **UI** (design specs) → **Security** + **Performance** (review arch) → **Coder** (implementation) → **Tester** + **Reviewer** (quality gates) → **Debugger** + **Refactor** (fix issues) → **UX Critic** (usability review) → **Product** (validation) → **Release** (versioning). **Docs Writer** updates docs after every agent. **Asset Gen** produces visual assets. **Validator** enforces process. **Bug Gatherer** collects reports. Conflict resolution priority: Product > Architecture > UI.

## Key Files

- `README.md` — Master index with full placeholder reference table and quick start guide
- `root/CLAUDE.md` — The CLAUDE.md template that gets placed in target projects (heavily parameterized)
- `agents/README.md` — Agent roster, interaction diagram, and per-milestone/per-task workflow
- `docs/README.md` — Documentation index listing all doc templates and their purposes

## Working With This Repo

- All files are markdown — there are no build, lint, or test commands
- Every template file begins with an HTML comment block (`<!-- TEMPLATE INSTRUCTIONS -->`) explaining how to customize it
- Agent files are self-contained; removing one does not break others
- `root/CLAUDE.md` contains `@import` directives at the bottom referencing docs that should be loaded as context
