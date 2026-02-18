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
claude/
  README.md              # This file — master index and usage guide
  root/                  # Files intended for the project root
  agents/                # Agent role definitions (copied to .claude/agents/)
  docs/                  # Shared reference documents for agents and developers
```

### root/

Files in this directory are copied directly to the root of the target project. They configure the development environment, define coding conventions, and provide the top-level context that every agent reads first.

### agents/

Each file defines one agent role with YAML frontmatter for Claude Code auto-discovery. When copied to `.claude/agents/` in the target project, Claude Code automatically registers them as subagents that can be invoked by name or delegated to automatically based on task type. Files that do not apply to your project type can be deleted without affecting the others.

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
| `[FRAMEWORK_VERSION]` | Framework version | v14, SDK 52 |
| `[LANGUAGE]` | Primary programming language | any typed or untyped language |
| `[STATE_LIBRARY]` | Client-side or application-level state management library | any state management solution |
| `[STATE_LIBRARY_VERSION]` | Version of the state management library | 4.x, 2.0 |
| `[PERSISTENCE_LAYER]` | Storage mechanism for application data | any database, file store, or cache |
| `[NAVIGATION_LIBRARY]` | Routing or navigation solution | React Router, GoRouter |
| `[TEST_RUNNER]` | Tool used to execute automated tests | any test runner or framework |
| `[PKG_MANAGER]` | Package or dependency manager | npm, pub, bundler |
| `[PKG_ADD_CMD]` | Command to add a new dependency | npm install, flutter pub add |
| `[PKG_MANIFEST]` | Package or dependency manifest file | package.json, pubspec.yaml |
| `[FRAMEWORK_CONFIG]` | Framework configuration file | app.json, next.config.js |
| `[TYPE_CONFIG]` | Type checker configuration file | tsconfig.json |
| `[BUNDLER_CONFIG]` | Bundler or build configuration file | metro.config.js, webpack.config.js |
| `[EXT]` | File extension for source files | tsx, dart, rb |

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

### Project Structure

| Placeholder | Description | Example value |
|---|---|---|
| `[SCREEN_DIR]` | Directory where screen or page files live | app/, pages/ |
| `[LOGIC_DIR]` | Directory for pure business logic | src/game/, lib/domain/ |
| `[STORE_DIR]` | Directory for state management files | src/store/ |
| `[COMPONENTS_DIR]` | Directory for UI components | src/components/ |
| `[HOOKS_DIR]` | Directory for reusable hooks or providers | src/hooks/ |
| `[CONSTANTS_DIR]` | Directory for constants and configuration | src/constants/ |
| `[ASSETS_DIR]` | Directory for static assets | assets/ |
| `[MAIN_SCREEN]` | Core feature screen file name | game, dashboard |

### Conventions

| Placeholder | Description | Example value |
|---|---|---|
| `[LOWER_CASE_CONVENTION]` | Naming convention for variables, functions, and file names | camelCase, snake_case |
| `[PASCAL_CASE_CONVENTION]` | Naming convention for types, interfaces, and components | PascalCase |
| `[UPPER_SNAKE_CONVENTION]` | Naming convention for module-level constants | UPPER_SNAKE_CASE |

### Persistence

| Placeholder | Description | Example value |
|---|---|---|
| `[SAVE_KEY]` | Storage key for persisted data | my_app_data_v1 |
| `[SAVE_VERSION]` | Current save format version number | 1 |

### Platform

| Placeholder | Description | Example value |
|---|---|---|
| `[TARGET_PLATFORMS]` | Comma-separated list of deployment targets | web, iOS, Android, desktop |
| `[PLATFORM_1]` | Primary target platform name | iOS |
| `[PLATFORM_2]` | Secondary target platform name | Android |
| `[TARGET_PLATFORM_1]` | First platform for Build & Test instructions | iOS simulator |
| `[TARGET_PLATFORM_2]` | Second platform for Build & Test instructions | Android emulator |
| `[TARGET_PLATFORM_3]` | Third platform for Build & Test instructions | web browser |
| `[INPUT_METHOD]` | Primary input method | touch, mouse, keyboard |
| `[MIN_TOUCH_TARGET]` | Minimum interactive element size for touch interfaces | any size specification in platform units |
| `[THEME_FILE_PATH]` | Relative path from the project root to the theme or design-token file | path to the project's theme constants |
| `[OTHER_DEP_1]` | Additional project dependency | any package name |
| `[OTHER_DEP_2]` | Additional project dependency | any package name |

### Testing

| Placeholder | Description | Example value |
|---|---|---|
| `[COVERAGE_TARGET]` | Minimum code coverage percentage threshold | 80% |
| `[BRANCH_TARGET]` | Minimum branch coverage percentage threshold | 80% |

### Performance

| Placeholder | Description | Example value |
|---|---|---|
| `[STARTUP_METRIC]` | Maximum acceptable app startup time | 2s |
| `[TICK_METRIC]` | Maximum acceptable update loop duration | 16ms |
| `[RENDER_METRIC]` | Maximum acceptable frame render time | 16ms |
| `[MEMORY_METRIC]` | Maximum acceptable memory usage | 200MB |
| `[STORAGE_METRIC]` | Maximum acceptable local storage usage | 50MB |

### Process

| Placeholder | Description | Example value |
|---|---|---|
| `[SESSION_TYPE]` | Type of user validation session | playtest, usability test, A/B test |
| `[MAX_AGE_DAYS]` | Maximum age in days before a task is flagged stale | 14 |
| `[MAX_BLOCKED_DAYS]` | Maximum days a task can remain blocked before escalation | 7 |
| `[CRITICAL_BLOCKED_DAYS]` | Maximum days a critical task can remain blocked | 3 |

### Agents

| Placeholder | Description | Example value |
|---|---|---|
| `[AI_MODEL]` | Identifier of the AI model used to power agents | any model identifier |
| `[MEDIA_TYPE]` | Category of generated or processed media assets | pixel art, SVG icons, 3D models, photography |

---

## Quick Start

1. **Copy template files** into the target project:

   ```
   cp root/CLAUDE.md /path/to/your-project/CLAUDE.md
   mkdir -p /path/to/your-project/.claude/agents
   cp agents/*.md /path/to/your-project/.claude/agents/
   cp -r docs/ /path/to/your-project/docs/
   ```

   Agent files in `.claude/agents/` are automatically discovered by Claude Code as subagents.

2. **Search for every placeholder** across all files and replace each one with the appropriate project-specific value. Process the placeholder categories in order: Identity first, then Tech, then Commands, then Domain, then Platform, then Agents.

3. **Delete optional agent files** that do not apply to your project. Each agent file is self-contained; removing one does not break the others. Refer to the Minimum Viable Agent Set section or the file listing below to identify candidates for deletion.

4. **Review the docs/** directory. Each document contains its own placeholder tokens. Fill them in with the same values used in the agent files to keep all references consistent.

5. **Commit the populated template** as part of your project's initial commit so that all contributors and agents share the same baseline context from the start.

6. **Verify all placeholders are replaced** by searching for remaining tokens:

   ```
   grep -r '\[' --include='*.md' . | grep -v 'node_modules' | grep '\[.*\]'
   ```

   Any remaining `[PLACEHOLDER]` tokens indicate incomplete customization.

7. **Remove this README** from your project once the template has been fully populated, or repurpose it as a contributor guide scoped to your specific project.

---

## Using with Claude Code

### Session Initialization

`CLAUDE.md` is automatically loaded from the project root at every session start. It provides the baseline context (project identity, build commands, conventions) that all agents need. Agent files in `.claude/agents/` are auto-discovered as subagents — no manual loading required.

### Agent Invocation

With agent files in `.claude/agents/`, Claude Code can invoke them in three ways:

1. **Automatic delegation** — Claude routes tasks to the matching subagent based on the `description` field in each agent's YAML frontmatter (e.g., asking "review this code" automatically delegates to the reviewer agent).
2. **Explicit request** — Ask Claude directly: "Use the coder agent to implement this feature" or "Have the security agent audit this module."
3. **Management** — Use the `/agents` command to view, create, and manage all available subagents.

### Agent Reference by Task Type

| Task | Agent |
|---|---|
| Define or update requirements | `product` |
| Design system architecture | `architect` |
| Design UI screens or components | `ui` |
| Implement features or fixes | `coder` |
| Review code quality | `reviewer` |
| Write or run tests | `tester` |
| Investigate a bug | `debugger` |
| File a bug report | `bug-gatherer` |
| Refactor code structure | `refactor` |
| Update documentation | `docs-writer` |
| Evaluate UX flows | `ux-critic` |
| Audit for security issues | `security` |
| Profile performance | `performance` |
| Prepare a release | `release` |
| Produce visual assets | `asset-gen` |
| Enforce process and resolve conflicts | `validator` |

### Inter-Agent Handoff

Agents communicate through shared documents. When one agent completes work, the next agent reads the updated files:

- **Current Work tables** in each agent file track in-progress and completed tasks.
- **`docs/BUGS.md`** is the shared bug tracker (Bug Gatherer files, Debugger investigates, Coder fixes).
- **Architecture documents** (`docs/ARCH_MODULE.md`, `docs/ARCH_DATA_SCHEMA.md`) are the contract between Architecture and Coder.
- **UI specifications** (`docs/UI_SPEC.md`) are the contract between UI and Coder.

### Minimum Viable Agent Set

These agents form the core development loop and are recommended for all projects:
- **Product** — Requirements and acceptance criteria
- **Coder** — Implementation
- **Reviewer** — Code quality
- **Tester** — Test coverage

Strongly recommended additions:
- **Architect** — For projects with multiple modules or complex structure
- **Debugger** — For projects with non-trivial bug investigation needs
- **Docs Writer** — For projects requiring documentation maintenance

Optional based on project type:
- **Security** — Security-critical applications
- **Performance** — Performance-sensitive applications
- **UX Critic** — User-facing applications with complex flows
- **Asset Gen** — Projects requiring visual asset production
- **Release** — Projects with formal release processes
- **Refactor** — Projects with technical debt concerns
- **Bug Gatherer** — Projects with external bug reporters
- **Validator** — Large teams or complex multi-agent workflows

---

## File Listing

All files in the template system are listed below with a short description of each file's purpose.

### root/ (1 file)

| File | Description |
|---|---|
| `root/CLAUDE.md` | Top-level context file read first by every agent; defines project identity, structure, conventions, and run commands |

### agents/ → `.claude/agents/` (17 files)

| File | Description |
|---|---|
| `agents/product.md` | Defines the product agent; owns requirements, acceptance criteria, milestone definitions, and final sign-off |
| `agents/architect.md` | Defines the system design agent; responsible for proposing and documenting structural decisions |
| `agents/ui.md` | Defines the UI agent; owns visual design, layout specifications, style guide, and interaction patterns |
| `agents/coder.md` | Defines the implementation agent; responsible for writing feature code within established conventions |
| `agents/reviewer.md` | Defines the code review agent; reviews everything the Coder produces against quality standards |
| `agents/tester.md` | Defines the testing agent; runs after every Coder change to generate and maintain automated test coverage |
| `agents/debugger.md` | Defines the debugging agent; investigates bugs, logs to docs/BUGS.md, explains defects and provides alternative solutions |
| `agents/refactor.md` | Defines the refactoring agent; improves code structure without changing behaviour, triggered by Reviewer/Tester issues or user |
| `agents/docs-writer.md` | Defines the documentation agent; updates docs after any agent completes work, accepts direct user input |
| `agents/ux-critic.md` | Defines the UX review agent; evaluates flows after Product and Coder, files issues with Bug Gatherer |
| `agents/security.md` | Defines the security audit agent; runs after Architecture changes or plans, identifies vulnerabilities |
| `agents/performance.md` | Defines the performance agent; runs after Architecture changes, provides feedback to Architecture |
| `agents/release.md` | Defines the release preparation agent; responsible for changelogs, versioning, and build verification |
| `agents/asset-gen.md` | Defines the media asset generation agent; responsible for specifying and producing visual assets |
| `agents/validator.md` | Defines the validator agent; enforces agent protocols, resolves conflicts, tracks milestones, runs retrospectives |
| `agents/bug-gatherer.md` | Defines the bug gatherer agent; collects and structures bug reports for Product triage and Coder resolution |
| `agents/README.md` | Master overview of the agent system: roster, interaction diagram, per-milestone and per-task workflows, and placeholder reference |

### docs/ (22 files)

| File | Description |
|---|---|
| `docs/README.md` | Documentation index; master navigation entry point for all project documentation |
| `docs/PRD.md` | Product Requirements Document; describes goals, user stories, and acceptance criteria for the current scope |
| `docs/CONCEPT.md` | High-level project vision, core loop, and design pillars |
| `docs/ADDITIONAL.md` | Supplementary context that does not fit the primary documents; captures edge cases and open questions |
| `docs/GLOSSARY.md` | Canonical definitions for all domain-specific terms used across documents |
| `docs/DESIGN_RATIONALE.md` | Decision log recording significant design choices and their trade-offs |
| `docs/CODE_PATTERNS.md` | Coding conventions, naming rules, module structure, and state management patterns |
| `docs/FILE_CONVENTIONS.md` | File naming rules, directory layout expectations, and module organisation guidelines |
| `docs/ERROR_HANDLING.md` | Guidelines for handling errors across all categories; defines principles, patterns, and user-facing message standards |
| `docs/TEST_FRAMEWORK.md` | Testing strategy, test runner setup, file conventions, and coverage requirements |
| `docs/BUGS.md` | Active bug tracker; documents known issues, reproduction steps, and resolution status |
| `docs/CHANGELOG.md` | Chronological log of notable changes across releases and milestones, maintained by the release agent |
| `docs/ASSETS.md` | Registry of all project assets (images, fonts, etc.) with status and source information |
| `docs/MVP_LAUNCH.md` | Checklist and criteria for the initial public release |
| `docs/STANDUP.md` | Running log of progress updates, blockers, and decisions from work sessions |
| `docs/MILESTONE_VALIDATION.md` | Acceptance records confirming each milestone has met its stated criteria |
| `docs/MILESTONE_TASKS.md` | Template for breaking a milestone into concrete, actionable tasks with acceptance criteria |
| `docs/MILESTONE_COMPLETION.md` | Template for milestone completion reports summarizing delivered items, deferrals, and lessons learned |
| `docs/ARCH_MODULE.md` | Template for documenting a single code module (purpose, interface, dependencies, error handling) |
| `docs/ARCH_SYSTEM.md` | Template for documenting a high-level system composed of multiple modules |
| `docs/ARCH_DATA_SCHEMA.md` | Template for documenting a data schema or save format |
| `docs/UI_SPEC.md` | Template for specifying a UI screen or component (layout, states, interactions, accessibility) |
