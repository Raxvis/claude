<!-- TEMPLATE INSTRUCTIONS
=========================
This is a template CLAUDE.md for AI assistant project instructions.

PURPOSE:
  CLAUDE.md is placed at the root of a project repository. It provides an AI coding
  assistant with persistent context about the project: what it is, how it is structured,
  what conventions to follow, and how to build and test it.

HOW TO FILL IN THIS TEMPLATE:
  1. Replace every [PLACEHOLDER] token with the actual project-specific value.
  2. Remove placeholder text and comments that no longer apply after filling in.
  3. Delete entire sections that are not relevant to your project (e.g. if your project
     has no progression/prestige system, remove that subsection).
  4. Expand any section with additional project-specific details as needed.
  5. Keep code examples in the style and syntax of your actual [LANGUAGE].
  6. Update the Memory Imports section to point to the docs that exist in your repo.

PLACEHOLDER LEGEND:
  The authoritative placeholder reference is in README.md at the repository root.
  This legend covers placeholders used in this file. See README.md for the full set.

  [PROJECT_NAME]          — The name of the project (e.g. "My App")
  [PROJECT_TYPE]          — What kind of product it is (e.g. "cross-platform mobile game",
                            "SaaS web application", "CLI tool")
  [FRAMEWORK]             — The primary framework (e.g. "Next.js", "Flutter", "Rails")
  [FRAMEWORK_VERSION]     — Framework version (e.g. "v14", "SDK 52")
  [LANGUAGE]              — Programming language (e.g. "TypeScript", "Dart", "Ruby")
  [STATE_LIBRARY]         — State management solution (e.g. "Redux", "Riverpod", "MobX")
  [STATE_LIBRARY_VERSION] — Version of the state library
  [PERSISTENCE_LAYER]     — How data is persisted locally (e.g. "SQLite", "IndexedDB",
                            "SharedPreferences")
  [NAVIGATION_LIBRARY]    — Routing/navigation solution (e.g. "React Router", "GoRouter")
  [TARGET_PLATFORMS]      — Deployment targets (e.g. "iOS, Android, Web")
  [DEV_SERVER_CMD]        — Command to start the dev server (e.g. "npm start", "flutter run")
  [TYPE_CHECK_CMD]        — Command to run the type checker (e.g. "npx tsc --noEmit")
  [TEST_CMD]              — Command to run the test suite (e.g. "npm test", "flutter test")
  [BUILD_CMD]             — Command to produce a production build
  [PKG_MANAGER]           — Package/dependency manager (e.g. "npm", "pub", "bundler")
  [PKG_ADD_CMD]           — How to add a new dependency (e.g. "npm install", "flutter pub add")
  [SAVE_KEY]              — Storage key for persisted data (e.g. "my_app_data_v1")
  [SAVE_VERSION]          — Current save format version number (e.g. "1")
  [SCREEN_DIR]            — Directory where screen/page files live (e.g. "app/", "pages/")
  [LOGIC_DIR]             — Directory for pure business logic (e.g. "src/game/", "lib/domain/")
  [STORE_DIR]             — Directory for state management files (e.g. "src/store/")
  [COMPONENTS_DIR]        — Directory for UI components (e.g. "src/components/")
  [HOOKS_DIR]             — Directory for reusable hooks/providers (e.g. "src/hooks/")
  [CONSTANTS_DIR]         — Directory for constants and config (e.g. "src/constants/")
  [ASSETS_DIR]            — Directory for static assets (e.g. "assets/")
  [EXT]                   — File extension for source files (e.g. "tsx", "dart", "rb")
  [MAIN_SCREEN]           — Core feature screen file name (e.g. "game", "dashboard")
  [FRAMEWORK_CONFIG]      — Framework configuration file (e.g. "app.json", "pubspec.yaml")
  [PKG_MANIFEST]          — Package/dependency manifest file (e.g. "package.json")
  [TYPE_CONFIG]           — Type checker configuration file (e.g. "tsconfig.json")
  [BUNDLER_CONFIG]        — Bundler/build configuration file (e.g. "metro.config.js",
                            "webpack.config.js")
  [LOWER_CASE_CONVENTION] — Naming convention for lowercase identifiers (e.g. "camelCase",
                            "snake_case")
  [PASCAL_CASE_CONVENTION] — Naming convention for type-level identifiers (e.g. "PascalCase")
  [UPPER_SNAKE_CONVENTION] — Naming convention for constants (e.g. "UPPER_SNAKE_CASE",
                             "SCREAMING_SNAKE_CASE")
  [INPUT_METHOD]          — Primary input method (e.g. "touch", "mouse", "keyboard")
  [MIN_TOUCH_TARGET]      — Minimum interactive element size (e.g. "44×44pt", "48dp")
  [OTHER_DEP_1]           — Additional project dependency (replace with actual package name)
  [OTHER_DEP_2]           — Additional project dependency (replace with actual package name)
  [TARGET_PLATFORM_1]     — First platform for Build & Test section (e.g. "iOS simulator")
  [TARGET_PLATFORM_2]     — Second platform for Build & Test section (e.g. "Android emulator")
  [TARGET_PLATFORM_3]     — Third platform for Build & Test section (e.g. "web browser")

After filling in the template, delete this entire comment block before committing.
=========================
-->

# [PROJECT_NAME] - CLAUDE.md

## Project Overview

[PROJECT_NAME] is a [PROJECT_TYPE] built with **[FRAMEWORK] ([FRAMEWORK_VERSION])**. Targets **[TARGET_PLATFORMS]**.

## Project Structure

```
[PROJECT_NAME]/
  [SCREEN_DIR]                    # Screen/page files ([NAVIGATION_LIBRARY] routing)
    _layout.[EXT]                 # Root layout: providers, navigator, theme
    index.[EXT]                   # Main menu / home screen
    [MAIN_SCREEN].[EXT]           # Core feature screen
    settings.[EXT]                # Settings screen
  src/
    [LOGIC_DIR]                   # Pure [LANGUAGE] business logic (no UI framework)
    [STORE_DIR]                   # [STATE_LIBRARY] store: all app state and actions
    [COMPONENTS_DIR]              # UI components
    [HOOKS_DIR]                   # Custom hooks / providers
    [CONSTANTS_DIR]
      theme.[EXT]                 # Colors, spacing, typography
  [ASSETS_DIR]
    images/                       # Image assets (icons, sprites, etc.)
  [FRAMEWORK_CONFIG]              # Framework config: name, slug, platforms, icons
  [PKG_MANIFEST]                  # Dependency manifest
  [TYPE_CONFIG]                   # [LANGUAGE] config (strict mode, path aliases)
  [BUNDLER_CONFIG]                # Bundler/build config
```

## Tech Stack

- **Framework**: [FRAMEWORK] ([FRAMEWORK_VERSION])
- **Language**: [LANGUAGE] (strict mode)
- **Navigation**: [NAVIGATION_LIBRARY] (file-based, stack navigator)
- **State Management**: [STATE_LIBRARY] ([STATE_LIBRARY_VERSION])
- **Persistence**: [PERSISTENCE_LAYER]
- **Platforms**: [TARGET_PLATFORMS]
- **Build**: `[DEV_SERVER_CMD]` (dev) / `[BUILD_CMD]` (production)

## [LANGUAGE] Style Conventions

> **Note:** Bracketed names in code examples below (e.g., `[MyComponent]`, `[DomainType]`,
> `[doAction]`) are illustrative example identifiers, not project placeholders. They show
> naming patterns you should follow using your own project-specific names.

- **[LOWER_CASE_CONVENTION]** for variables, functions, and file names
- **[PASCAL_CASE_CONVENTION]** for types, interfaces, UI components, and enums
- **[UPPER_SNAKE_CONVENTION]** for module-level constants
- Prefer structured type declarations over anonymous shapes for object types
- Prefer union/alias constructs for non-object types
- Explicit return types on all exported functions
- No unchecked/unsafe types — use proper types or a safe unknown equivalent
- All business logic in pure [LANGUAGE] modules (no UI framework), testable independently

```
// Pure logic module pattern
export struct/interface [DomainType] {
  [field_one]: [FieldType]
  [field_two]: [FieldType]
}

const [CONSTANT_NAME]: [Type] = [value]

function [internalHelper]([param]: [DomainType]): [DomainType] {
  // internal helper — not exported
}

export function [publicOperation](a: [DomainType], b: [DomainType]): [DomainType] {
  // ...
}
```

### UI Component Pattern

```
import { [UIComponents] } from '[FRAMEWORK]'
import { [Colors], [Spacing] } from '../[CONSTANTS_DIR]/theme'

interface [MyComponent]Props {
  value: [ValueType]
  onPress: () => void
}

export function [MyComponent]({ value, onPress }: [MyComponent]Props) {
  return (
    <[PressableComponent]
      style={[styles.container]}
      onPress={onPress}
      accessibilityLabel="[Descriptive label]"
    >
      <[TextComponent] style={[styles.text]}>{value}<[/TextComponent]>
    <[/PressableComponent]>
  )
}

const styles = [StyleHelper].create({
  container: {
    backgroundColor: [Colors].surface,
    padding: [Spacing].md,
  },
  text: {
    color: [Colors].textPrimary,
  },
})
```

## Architecture

### Navigation ([NAVIGATION_LIBRARY])

File-based routing in `[SCREEN_DIR]`. Navigate between screens using the router API:

```
import { router } from '[NAVIGATION_LIBRARY]'

// Navigate forward
router.push('/[MAIN_SCREEN]')

// Go back
router.back()

// Navigate with parameters
router.push({ pathname: '/[MAIN_SCREEN]', params: { mode: '[MODE_VALUE]' } })
```

Screen files:
- `[SCREEN_DIR]/index.[EXT]` — Main menu (title, start button, settings)
- `[SCREEN_DIR]/[MAIN_SCREEN].[EXT]` — Core gameplay / feature screen + HUD
- `[SCREEN_DIR]/settings.[EXT]` — Settings / options

### State Management ([STATE_LIBRARY])

All application state lives in `[STORE_DIR]`. UI components read via selectors; actions mutate state:

```
import { useStore } from '../[STORE_DIR]/store'

// Read a state slice
const [currency] = useStore((s) => s.[currency])

// Call an action
const [doAction] = useStore((s) => s.[doAction])
[doAction]()
```

Prefer fine-grained selectors over subscribing to the whole store to avoid unnecessary re-renders.

## Domain-Specific Patterns

_Add domain-specific patterns here that are unique to your project. Delete this placeholder
section and replace it with patterns relevant to your domain. Examples of domain-specific
patterns: custom data types, calculation engines, scheduling logic, workflow state machines,
real-time update loops, or any business logic that warrants a documented convention._

## Persistence

Data is persisted via [PERSISTENCE_LAYER] using the key `[SAVE_KEY]`.

- Include a `version` field in persisted data for migration support
- Always handle missing or corrupt data gracefully by falling back to defaults
- The save format must support forward migration (see `save-manager.[EXT]`)

## Performance

- **Scrolling lists**: Use virtualized list components; implement stable key extraction and memoized render functions
- **Re-renders**: Fine-grained [STATE_LIBRARY] selectors prevent unnecessary re-renders
- **Images**: Use appropriate resizing and consider a caching-aware image component
- **Style definitions**: Always use the framework's style creation helper — avoids recreating objects on every render
- **Avoid inline styles** that recreate objects on every render cycle
- **Platform-specific values**: Use platform conditional helpers for values that differ per platform
- **Large lists**: For lists exceeding ~100 items, tune windowing/virtualization parameters
- **Memory**: Avoid storing large derived arrays in state; prefer computed selectors

## Input Handling

[INPUT_METHOD]-based interaction. Use the framework's recommended pressable primitive for all interactive elements:

```
<[PressableComponent]
  style={({ pressed }) => [[styles.button], pressed && [styles.pressed]]}
  onPress={handlePress}
  accessibilityLabel="[Descriptive action label]"
>
  <[TextComponent]>[Button Label]<[/TextComponent]>
<[/PressableComponent]>
```

- All interactive elements: minimum [MIN_TOUCH_TARGET] touch/click target size
- Provide visual pressed feedback (scale transform or opacity change)
- Account for system UI intrusions (notches, safe areas, status bars) using the platform insets API
- Web: add pointer cursor style via platform conditional in style definitions

## Git Workflow

- **Branching**: Feature branches off `main`, merged via pull request
- **Branch naming**: `feature/description`, `fix/description`, `refactor/description`
- **Commits**: Short imperative messages (e.g., "Add [FEATURE]", "Fix [BUG_DESCRIPTION]")
- **Ignore**: Build outputs, dependency directories, local environment files (already in `.gitignore`)

## Dependencies

Manage with `[PKG_MANAGER]`. Add new dependencies:

```bash
[PKG_ADD_CMD] <package>   # preferred for framework-managed packages
[PKG_MANAGER] install <package>  # for generic packages
```

Current dependencies (see `[PKG_MANIFEST]`):
- **[FRAMEWORK]** — core SDK
- **[NAVIGATION_LIBRARY]** — routing / navigation
- **[STATE_LIBRARY]** — state management
- **[PERSISTENCE_LAYER]** — local persistence
- **[OTHER_DEP_1]** — [description]
- **[OTHER_DEP_2]** — [description]

## Common Pitfalls

- **[STATE_LIBRARY] selectors**: Always use selector functions — never subscribe to the entire store root, which triggers re-renders on every state change.
- **Effect cleanup**: Always return a cleanup function from lifecycle effects that set up intervals or event listeners to prevent memory leaks.
- **Safe area**: Always account for system UI insets — device notches and status bars require padding adjustments.
- **Platform API gaps**: Some framework APIs may not be available on all target platforms. Use platform conditional guards where needed.
- **[NAVIGATION_LIBRARY] routing**: Screen files must live in `[SCREEN_DIR]`. The layout file configures the navigator for that directory.

## Build & Test

- **Dev server**: `[DEV_SERVER_CMD]`
  - Open in [TARGET_PLATFORM_1]
  - Open in [TARGET_PLATFORM_2]
  - Open in [TARGET_PLATFORM_3]
- **Type check**: `[TYPE_CHECK_CMD]`
- **Tests**: `[TEST_CMD]`
- **Production build**: `[BUILD_CMD]`
- **Debug**: Use [FRAMEWORK] DevTools / dev menu, or runtime logging
- **Hot reload**: [FRAMEWORK] supports fast refresh for instant iteration

## File Naming

- [LOWER_CASE_CONVENTION] for source files: `[example-module].[EXT]`, `[example-store].[EXT]`
- [PASCAL_CASE_CONVENTION] for UI components: `[ExampleView].[EXT]`, `[ExampleCard].[EXT]`
- Group by feature as the project grows:
  ```
  src/
    [LOGIC_DIR]       # Pure [LANGUAGE] business logic
    [STORE_DIR]       # [STATE_LIBRARY] store
    [COMPONENTS_DIR]  # UI components
    [HOOKS_DIR]       # Custom hooks / providers
    [CONSTANTS_DIR]   # Theme, config, constants
  [SCREEN_DIR]        # [NAVIGATION_LIBRARY] screen files
  ```

## Memory Imports
@import docs/README.md
@import docs/PRD.md
@import docs/CONCEPT.md
@import docs/ADDITIONAL.md
@import docs/FILE_CONVENTIONS.md
