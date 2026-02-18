<!-- TEMPLATE INSTRUCTIONS
  This file is the master index for the reusable project template system.
  It describes the purpose, structure, placeholder conventions, and file inventory
  for every template file in this directory tree.

  When adapting this template to a new project:
    1. Read this file in full before touching anything else.
    2. Follow the Quick Start section below.
    3. Replace every [PLACEHOLDER_NAME] token with a project-specific value.
    4. Delete agent files that are not relevant to your project type.
    5. Remove this comment block from the final project's copy of the file.
-->

# Project Template System

## What Is This?

This is a **multi-agent AI-assisted development workflow template**. It provides a structured set of documents and agent configuration files that can be dropped into any new software project to establish a consistent, repeatable development process from day one.

The template is designed to be used with AI coding assistants running as autonomous or semi-autonomous agents. Each agent file defines a focused role (e.g., architect, reviewer, tester) and a set of responsibilities scoped to one part of the development lifecycle. The supporting documents provide the shared context those agents need to operate coherently across a project.

The system is:

- **Technology-agnostic** — placeholders stand in for every stack-specific detail.
- **Domain-agnostic** — placeholder names cover a wide range of application domains.
- **Incremental** — adopt only the agent roles and documents that apply to your project phase.

---

## Directory Structure

```
template/
  README.md              # This file — master index and usage guide
  root/                  # Files intended for the project root
  agents/                # Agent role definition files
  docs/                  # Shared reference documents for agents and developers
```

### root/

Files in this directory are copied directly to the root of the target project. They configure the development environment, define coding conventions, and provide the top-level context that every agent reads first.

### agents/

Each file defines one agent role. An agent file specifies the agent's purpose, its inputs and outputs, the decisions it is authorised to make autonomously, and the decisions that require human approval. Files that do not apply to your project type can be deleted without affecting the others.

### docs/

Supporting reference documents. These are not agent definitions — they are shared knowledge that multiple agents and human contributors reference. They cover topics such as architecture decisions, domain rules, API contracts, and quality standards.

---

## Placeholder Convention

All project-specific content in template files is expressed using square-bracket placeholder tokens:

```
[PLACEHOLDER_NAME]
```

Placeholders appear inline within prose, code blocks, file paths, and configuration values. Every placeholder in every file must be replaced before the template is put into active use. Leaving a placeholder in place causes agents to emit that token literally, which produces incorrect output.

Placeholder names are written in `UPPER_SNAKE_CASE` and are scoped to one of the categories below.

---

## Placeholder Reference

### Identity

| Placeholder | Description | Example value |
|---|---|---|
| `[PROJECT_NAME]` | Human-readable name of the project | Acme Dashboard |
| `[PROJECT_TYPE]` | Category of software being built | mobile app, CLI tool, web service |
| `[ONE_SENTENCE_PITCH]` | Single sentence describing what the product does and for whom | A budgeting tool that helps freelancers track project income in real time |

### Tech

| Placeholder | Description | Example value |
|---|---|---|
| `[FRAMEWORK]` | Primary application framework | any client or server framework |
| `[LANGUAGE]` | Primary programming language | any typed or untyped language |
| `[STATE_LIBRARY]` | Client-side or application-level state management library | any state management solution |
| `[PERSISTENCE_LAYER]` | Storage mechanism for application data | any database, file store, or cache |
| `[TEST_RUNNER]` | Tool used to execute automated tests | any test runner or framework |

### Commands

| Placeholder | Description | Example value |
|---|---|---|
| `[DEV_SERVER_CMD]` | Command to start the local development server | the project's start/watch command |
| `[TYPE_CHECK_CMD]` | Command to run the static type checker without emitting output | the project's type-check command |
| `[TEST_CMD]` | Command to execute the full test suite | the project's test command |
| `[BUILD_CMD]` | Command to produce a production build artifact | the project's build command |

### Domain

| Placeholder | Description | Example value |
|---|---|---|
| `[DOMAIN_ENTITY]` | The primary data object the application manages | order, patient record, task, asset |
| `[RESOURCE_TYPE]` | A secondary resource that belongs to or relates to the domain entity | line item, appointment, subtask, attachment |
| `[CORE_MECHANIC]` | The central user-facing action or loop in the application | placing a bid, scheduling a shift, publishing a report |
| `[PROGRESSION_UNIT]` | The measure of progress or achievement that users accumulate | points, completed milestones, unlocked tiers |

### Platform

| Placeholder | Description | Example value |
|---|---|---|
| `[TARGET_PLATFORMS]` | Comma-separated list of deployment targets | web, iOS, Android, desktop |
| `[TOUCH_TARGET_SIZE]` | Minimum interactive element size for touch interfaces | any size specification in platform units |
| `[THEME_FILE_PATH]` | Relative path from the project root to the theme or design-token file | path to the project's theme constants |

### Agents

| Placeholder | Description | Example value |
|---|---|---|
| `[AI_MODEL]` | Identifier of the AI model used to power agents | any model identifier |
| `[MEDIA_TYPE]` | Category of generated or processed media assets | pixel art, SVG icons, 3D models, photography |

---

## Quick Start

1. **Copy the template directory** into the root of your new project repository:

   ```
   cp -r template/ /path/to/your-new-project/template/
   ```

2. **Search for every placeholder** across all files and replace each one with the appropriate project-specific value. Process the placeholder categories in order: Identity first, then Tech, then Commands, then Domain, then Platform, then Agents.

3. **Delete optional agent files** that do not apply to your project. Each agent file is self-contained; removing one does not break the others. Refer to the file listing below to identify candidates for deletion.

4. **Review the docs/** directory. Each document contains its own placeholder tokens. Fill them in with the same values used in the agent files to keep all references consistent.

5. **Commit the populated template** as part of your project's initial commit so that all contributors and agents share the same baseline context from the start.

6. **Remove this README** from your project once the template has been fully populated, or repurpose it as a contributor guide scoped to your specific project.

---

## File Listing

All 28 files in the template system are listed below with a short description of each file's purpose.

### root/ (8 files)

| File | Description |
|---|---|
| `root/CLAUDE.md` | Top-level context file read first by every agent; defines project identity, structure, conventions, and run commands |
| `root/.gitignore` | Standard ignore rules for build artifacts, secrets, and generated files |
| `root/tsconfig.json` | Compiler configuration for strict static type checking |
| `root/babel.config.js` | Transpiler configuration for the framework's build pipeline |
| `root/metro.config.js` | Bundler configuration for module resolution and asset handling |
| `root/app.json` | Application manifest: name, identifier, icon references, platform targets |
| `root/package.json` | Dependency manifest and npm script definitions |
| `root/.env.example` | Template for environment variable definitions; contains no real secrets |

### agents/ (12 files)

| File | Description |
|---|---|
| `agents/architect.md` | Defines the system design agent; responsible for proposing and documenting structural decisions |
| `agents/coder.md` | Defines the implementation agent; responsible for writing feature code within established conventions |
| `agents/reviewer.md` | Defines the code review agent; responsible for evaluating pull requests against quality standards |
| `agents/tester.md` | Defines the testing agent; responsible for generating and maintaining automated test coverage |
| `agents/debugger.md` | Defines the debugging agent; responsible for isolating and explaining defects |
| `agents/refactor.md` | Defines the refactoring agent; responsible for improving code structure without changing behaviour |
| `agents/docs-writer.md` | Defines the documentation agent; responsible for producing and maintaining developer-facing documentation |
| `agents/ux-critic.md` | Defines the user experience review agent; responsible for evaluating flows against usability heuristics |
| `agents/security.md` | Defines the security audit agent; responsible for identifying vulnerabilities and insecure patterns |
| `agents/performance.md` | Defines the performance agent; responsible for profiling, identifying bottlenecks, and proposing optimisations |
| `agents/release.md` | Defines the release preparation agent; responsible for changelogs, versioning, and build verification |
| `agents/asset-gen.md` | Defines the media asset generation agent; responsible for specifying and producing visual or audio assets |

### docs/ (8 files)

| File | Description |
|---|---|
| `docs/PRD.md` | Product Requirements Document; describes goals, user stories, and acceptance criteria for the current scope |
| `docs/ARCHITECTURE.md` | Architecture decision record; documents structural choices, data flow, and module boundaries |
| `docs/GAME.md` | Domain rules and mechanics reference; describes the core logic and progression system in plain language |
| `docs/ADDITIONAL.md` | Supplementary context that does not fit the primary documents; captures edge cases and open questions |
| `docs/FILE_CONVENTIONS.md` | File naming rules, directory layout expectations, and module organisation guidelines |
| `docs/API_CONTRACT.md` | Specifies the interfaces between major modules or external services; includes request/response shapes |
| `docs/QUALITY_STANDARDS.md` | Defines measurable quality targets: coverage thresholds, performance budgets, accessibility requirements |
| `docs/CHANGELOG.md` | Running log of notable changes per release version, maintained by the release agent |
