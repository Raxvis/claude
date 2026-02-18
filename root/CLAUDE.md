<!-- TEMPLATE INSTRUCTIONS
  FILE: CLAUDE.md (placed at project root)
  PURPOSE: Provides an AI coding assistant with persistent context about the project.

  HOW TO CUSTOMIZE:
  - Replace every [PLACEHOLDER] token with project-specific values.
  - See README.md for the full placeholder reference table.
  - Delete sections not relevant to your project.
  - Update Memory Imports to match your actual docs.
  - Delete this comment block before committing.
-->

# [PROJECT_NAME] - CLAUDE.md

## Project Overview

[PROJECT_NAME] is a [PROJECT_TYPE] built with **[FRAMEWORK] ([FRAMEWORK_VERSION])**. Targets **[TARGET_PLATFORMS]**.

## Tech Stack

- **Framework**: [FRAMEWORK] ([FRAMEWORK_VERSION])
- **Language**: [LANGUAGE] (strict mode)
- **Navigation**: [NAVIGATION_LIBRARY] (file-based, stack navigator)
- **State Management**: [STATE_LIBRARY] ([STATE_LIBRARY_VERSION])
- **Persistence**: [PERSISTENCE_LAYER]
- **Platforms**: [TARGET_PLATFORMS]
- **Build**: `[DEV_SERVER_CMD]` (dev) / `[BUILD_CMD]` (production)

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

## Common Pitfalls

- **[STATE_LIBRARY] selectors**: Always use selector functions — never subscribe to the entire store root, which triggers re-renders on every state change.
- **Effect cleanup**: Always return a cleanup function from lifecycle effects that set up intervals or event listeners to prevent memory leaks.
- **Safe area**: Always account for system UI insets — device notches and status bars require padding adjustments.
- **Platform API gaps**: Some framework APIs may not be available on all target platforms. Use platform conditional guards where needed.
- **[NAVIGATION_LIBRARY] routing**: Screen files must live in `[SCREEN_DIR]`. The layout file configures the navigator for that directory.

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

_This section applies to user-facing applications (mobile, web, desktop). For CLI tools or backend services, delete this section._

- **Scrolling lists**: Use virtualized list components; implement stable key extraction and memoized render functions
- **Re-renders**: Fine-grained [STATE_LIBRARY] selectors prevent unnecessary re-renders
- **Images**: Use appropriate resizing and consider a caching-aware image component
- **Style definitions**: Always use the framework's style creation helper — avoids recreating objects on every render
- **Avoid inline styles** that recreate objects on every render cycle
- **Platform-specific values**: Use platform conditional helpers for values that differ per platform
- **Large lists**: For lists exceeding ~100 items, tune windowing/virtualization parameters
- **Memory**: Avoid storing large derived arrays in state; prefer computed selectors

## Input Handling

_This section applies to user-facing applications (mobile, web, desktop). For CLI tools or backend services, delete this section._

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

These documents are loaded into Claude Code's context at every session start.
They provide the baseline context all agents need. Customize based on your
project's needs — add docs your agents frequently reference, remove any that
don't apply.

<!-- Core context: documentation index, requirements, coding patterns, file rules, error handling -->
@import docs/README.md
@import docs/PRD.md
@import docs/CODE_PATTERNS.md
@import docs/FILE_CONVENTIONS.md
@import docs/ERROR_HANDLING.md

<!-- Consider adding once they contain real project content:
@import docs/CONCEPT.md
@import docs/ADDITIONAL.md
@import docs/GLOSSARY.md
-->
