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
  [MONETIZATION_MODEL]    — How the product is monetized (e.g. "IAP only", "subscription",
                            "freemium with ads")
  [DEV_SERVER_CMD]        — Command to start the dev server (e.g. "npm start", "flutter run")
  [TYPE_CHECK_CMD]        — Command to run the type checker (e.g. "npx tsc --noEmit")
  [TEST_CMD]              — Command to run the test suite (e.g. "npm test", "flutter test")
  [BUILD_CMD]             — Command to produce a production build
  [PKG_MANAGER]           — Package/dependency manager (e.g. "npm", "pub", "bundler")
  [PKG_ADD_CMD]           — How to add a new dependency (e.g. "npm install", "flutter pub add")
  [SAVE_KEY]              — Storage key for persisted save data (e.g. "my_app_save_v1")
  [SAVE_VERSION]          — Current save format version number (e.g. "1")
  [BUNDLE_ID]             — Application bundle/package identifier
  [TICK_INTERVAL_MS]      — Main loop tick interval in milliseconds (e.g. "500")
  [OFFLINE_CAP_HOURS]     — Maximum offline progress hours to award (e.g. "8")
  [COST_GROWTH_RATE]      — Exponential cost scaling growth rate (e.g. "1.10")
  [SCREEN_DIR]            — Directory where screen/page files live (e.g. "app/", "pages/")
  [LOGIC_DIR]             — Directory for pure business logic (e.g. "src/game/", "lib/domain/")
  [STORE_DIR]             — Directory for state management files (e.g. "src/store/")
  [COMPONENTS_DIR]        — Directory for UI components (e.g. "src/components/")
  [HOOKS_DIR]             — Directory for reusable hooks/providers (e.g. "src/hooks/")
  [CONSTANTS_DIR]         — Directory for constants and config (e.g. "src/constants/")
  [ASSETS_DIR]            — Directory for static assets (e.g. "assets/")

After filling in the template, delete this entire comment block before committing.
=========================
-->

# [PROJECT_NAME] - CLAUDE.md

## Project Overview

[PROJECT_NAME] is a [PROJECT_TYPE] built with **[FRAMEWORK] ([FRAMEWORK_VERSION])**. Targets **[TARGET_PLATFORMS]**. Monetized via **[MONETIZATION_MODEL]**.

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
      [LARGE_NUMBER_MODULE].[EXT] # Large-number arithmetic + formatting
      [ENTITY_DATA_MODULE].[EXT]  # Static entity definitions and calculations
      [WORLD_DATA_MODULE].[EXT]   # World/level/slot data structures and mutations
      economy.[EXT]               # Revenue tick calculations
      save-manager.[EXT]          # [PERSISTENCE_LAYER] persistence, offline progress
    [STORE_DIR]
      [APP_STORE].[EXT]           # [STATE_LIBRARY] store: all app state and actions
    [COMPONENTS_DIR]              # UI components
    [HOOKS_DIR]
      use[MainLoop].[EXT]         # [TICK_INTERVAL_MS]ms main loop hook
      use[OfflineProgress].[EXT]  # Background/foreground listener for offline earnings
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
- `[SCREEN_DIR]/[SHOP_SCREEN].[EXT]` — Purchases / store (future)

### State Management ([STATE_LIBRARY])

All application state lives in `[STORE_DIR]/[APP_STORE].[EXT]`. UI components read via selectors; actions mutate state:

```
import { use[AppStore] } from '../[STORE_DIR]/[APP_STORE]'

// Read a state slice
const [currency] = use[AppStore]((s) => s.[currency])

// Call an action
const [doAction] = use[AppStore]((s) => s.[doAction])
[doAction]()
```

Prefer fine-grained selectors over subscribing to the whole store to avoid unnecessary re-renders.

## Domain-Specific Patterns

### Large Number Handling

Native numeric types lose precision for very large values. Use a custom large-number representation throughout:

```
// [LOGIC_DIR]/[LARGE_NUMBER_MODULE].[EXT]
export struct/interface [LargeNumber] {
  mantissa: [FloatType]   // range [1, 10) or exactly 0
  exponent: [IntType]     // power of 10
}

// e.g., 1.5 × 10^12 = 1,500,000,000,000

export function [largeNum](mantissa: [FloatType], exponent = 0): [LargeNumber]
export function [add](a: [LargeNumber], b: [LargeNumber]): [LargeNumber]
export function [subtract](a: [LargeNumber], b: [LargeNumber]): [LargeNumber]
export function [multiplyScalar](a: [LargeNumber], scalar: [FloatType]): [LargeNumber]
export function [greaterThanOrEqual](a: [LargeNumber], b: [LargeNumber]): [BoolType]
export function [format](n: [LargeNumber]): [StringType]  // → "1.5T", "2.3M", "500"
```

The [LargeNumber] struct should be a plain serializable object with no special encoding needed for [PERSISTENCE_LAYER].

### Offline Progress Calculation

```
// [LOGIC_DIR]/save-manager.[EXT]
const MAX_OFFLINE_SECONDS = [OFFLINE_CAP_HOURS] * 60 * 60  // [OFFLINE_CAP_HOURS]-hour cap

export function calculateOfflineProgress(save: [SaveData], now = currentUnixSeconds()) {
  const rawElapsed = now - save.lastSaveTime
  const elapsedSeconds = clamp(rawElapsed, 0, MAX_OFFLINE_SECONDS)
  const [resourcePerSecond] = calculate[Resource]PerSecond(save.[worldState])
  const earnings = [multiplyScalar]([resourcePerSecond], elapsedSeconds)
  return { elapsedSeconds, earnings }
}
```

Key considerations:
- Always cap offline time ([OFFLINE_CAP_HOURS]–24 hours) to prevent exploits
- Use wall-clock Unix seconds for timestamps, never frame-based time
- Calculation must be deterministic — avoid randomness in offline calculation
- Save `lastSaveTime` on every save and whenever the app goes to background

### Progression / Rebirth System

```
function calculate[PrestigeCurrency](lifetimeEarnings: [LargeNumber]): [IntType] {
  // sqrt-based scaling: first rebirth at ~[FIRST_PRESTIGE_MILESTONE] grants ~[FIRST_PRESTIGE_REWARD] tokens
  return floor(sqrt(toNumber(lifetimeEarnings) / [PRESTIGE_THRESHOLD]))
}
```

Design principles:
- Rebirth is permanent: [PERMANENT_IAP_ITEMS] and lifetime stats persist across resets
- Prestige multipliers stack multiplicatively with base production
- Soft cap on progression depth increases with each prestige tier

### Economy Balancing

- Exponential cost scaling: `base_cost * [COST_GROWTH_RATE] ^ level`
- Growth rate [COST_GROWTH_RATE] for [ENTITY_TYPE] upgrades
- Resource income scales slightly slower than costs to create meaningful decisions
- [DEMAND_METRIC] scales logarithmically: `log(total_[ENTITIES] + 1)`
- Main tick: [TICK_INTERVAL_MS]ms interval via `use[MainLoop]` hook

### Main Loop

```
// [HOOKS_DIR]/use[MainLoop].[EXT]
onMount/useEffect(() => {
  if (!isLoaded) return
  const id = setInterval(() => {
    applyTick()    // economy tick → update [currency] in store
    autoSave()     // every ~[AUTOSAVE_INTERVAL_SECONDS]s
  }, [TICK_INTERVAL_MS])
  return () => clearInterval(id)
}, [isLoaded])
```

- [TICK_INTERVAL_MS]ms tick interval for game/business logic
- UI re-renders driven by [STATE_LIBRARY] state subscriptions (no manual frame loop)
- `use[OfflineProgress]` hook uses the platform background/foreground event API to detect app state changes

## Persistence / Save System

### Local Saves ([PERSISTENCE_LAYER])

```
// [LOGIC_DIR]/save-manager.[EXT]
const SAVE_KEY = '[SAVE_KEY]'

export struct/interface [SaveData] {
  version: [IntType]
  [currency]: [LargeNumber]
  [worldState]: [WorldDataType]
  lastSaveTime: [IntType]      // Unix seconds
  [lifetimeMetric]: [LargeNumber]
}

export async function saveGame(data: [SaveData]): [VoidPromise] {
  const toSave = { ...data, lastSaveTime: currentUnixSeconds() }
  await [PERSISTENCE_LAYER].set([SAVE_KEY], serialize(toSave))
}

export async function loadGame(): [SaveDataPromise] {
  try {
    const raw = await [PERSISTENCE_LAYER].get([SAVE_KEY])
    if (!raw) return createDefaultSave()
    return migrateSave(deserialize(raw))
  } catch {
    return createDefaultSave()
  }
}
```

- Auto-save every [AUTOSAVE_INTERVAL_SECONDS] seconds via `use[MainLoop]`
- Save on app backgrounding via background-state listener in `use[OfflineProgress]`
- Include `version` field for migration support
- Always handle missing or corrupt save data gracefully by falling back to defaults

### Save Data Migration

```
const SAVE_VERSION = [SAVE_VERSION]

function migrateSave(data: [SaveData]): [SaveData] {
  if (data.version === [SAVE_VERSION]) {
    return { ...createDefaultSave(), ...data, version: [SAVE_VERSION] }
  }
  // Add version-specific migration branches here as the format evolves
  return createDefaultSave()
}
```

### Cloud Sync (Post-Launch)

- Not in MVP; planned for post-launch
- Will use [CLOUD_SYNC_PROVIDER] or a backend; local save always serves as fallback

## In-App Purchases (IAP)

Use `[IAP_LIBRARY]`:

```
// Product IDs as constants
const PRODUCTS = {
  [PRODUCT_KEY_1]: '[BUNDLE_ID].[product_slug_1]',
  [PRODUCT_KEY_2]: '[BUNDLE_ID].[product_slug_2]',
  // ...
}
```

- Validate receipts server-side when possible
- Handle purchase restoration (required for platform app stores)
- Store purchase state locally AND verify on load
- [PERMANENT_IAP_ITEMS] persist through prestige/rebirth resets

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

[ORIENTATION] orientation, [INPUT_METHOD]-based. Use the framework's recommended pressable primitive for all interactive elements:

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
- **[PLATFORM_WEB_COMPAT]** — web platform support (if applicable)
- **[SAFE_AREA_LIB]** — system inset / safe area handling
- **[OTHER_DEP_1]** — [description]
- **[OTHER_DEP_2]** — [description]

## Common Pitfalls

- **[LargeNumber] serialization**: Ensure the [LargeNumber] struct is a plain serializable object. Verify round-trip through [PERSISTENCE_LAYER] without loss of precision.
- **[STATE_LIBRARY] selectors**: Always use selector functions — never subscribe to the entire store root, which triggers re-renders on every state change.
- **Effect cleanup**: Always return a cleanup function from lifecycle effects that set up intervals or event listeners to prevent memory leaks.
- **Background state on web**: The background/foreground event API may behave differently on web (page visibility API). Test offline progress on web separately.
- **Wall-clock vs frame time**: Use Unix second timestamps for save times and offline progress. Never use frame-based or performance timers for persistence.
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
@import docs/PRD.md
@import docs/CONCEPT.md
@import docs/ADDITIONAL.md
@import docs/FILE_CONVENTIONS.md
