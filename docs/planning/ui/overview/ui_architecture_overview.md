# UI Architecture Overview

---

## 🎯 Purpose
Define the high-level architecture, responsibilities, and constraints of the EndlessOS UI, including how it interacts with backend services, how layers are structured, and how performance, security, and future scalability are preserved.

---

## Scope
- Includes: UI layers, UI–backend interaction model, UI data contracts, navigation model, performance and caching strategy, security posture, observability, and future expansion areas.
- Excludes: Detailed component specs, visual design tokens, platform-specific business logic, and low-level rendering engine implementation.

---

## Summary
The EndlessOS UI is a console-inspired, calm, high-contrast interface built around a Hub-as-world-selector model. It is layered, deterministic, and data-driven, with all backend interaction flowing through a single UI-Service (BFF) that shapes, sanitizes, and versions data for the UI. Navigation is global and stack-based, performance is protected by strict budgets and caching strategies, and security is enforced at the UI-Service boundary.

---

## Core Principles / System Goals
- **Single UI-Service Boundary:** The UI never calls platform services directly; all calls go through a single UI-Service (BFF).
- **Strict Layering:** UI layers (background, platform, utility, radial wheel, modals, system alerts) are strictly ordered and have clear responsibilities.
- **Data Shaping & Contracts:** The UI-Service shapes canonical backend data into UI-ready structures with explicit schema versions.
- **Global Navigation Stack:** Navigation is global, Hub-rooted, and deterministic, with navigation metadata provided by the UI-Service.
- **Performance First:** Cold/Hot path separation, caching, minimal re-rendering, and strict performance budgets keep the UI responsive.
- **Security at the Edge:** The UI-Service enforces auth, permissions, membership, parental controls, and zero-moderation rules.
- **Predictable Behavior:** Deterministic rendering, state machines, and a clear error/fallback model ensure stable, console-like UX.
- **Future-Proofing:** The architecture anticipates new platforms, surfaces, backgrounds, feature flags, and accessibility without rewrites.

---

## Components

### UI Layers
- **Background Layer**
  - Renders hub and platform backgrounds.
  - Never handles input directly.
  - Must load quickly and respect asset budgets.

- **Platform Layer**
  - Renders platform pages (Games, Music, Tube, etc.).
  - Owns platform-specific tiles, lists, and content views.
  - Consumes shaped data from the UI-Service.

- **Utility Layer**
  - Renders utility pages (settings, account, support, etc.).
  - Overlays or coexists with platform content depending on context.
  - Uses the same data contracts and navigation model as platforms.

- **Radial Wheel Layer**
  - Provides quick access to utilities, actions, or platform-local tools.
  - Always appears above platform and utility layers.
  - Must respect navigation and input rules.

- **Modal Layer**
  - Renders global, platform-local, and utility modals.
  - Always appears above all content layers.
  - Must follow strict modal rules (no modal chaos, no nested modals without explicit design).

- **System Alert Layer**
  - Renders critical alerts (errors, blocking prompts).
  - Highest priority and topmost layer.
  - Used sparingly and consistently.

### UI-Service (BFF)
- Single public-facing service for all UI clients.
- Shapes canonical backend data into UI-ready structures (tiles, carousels, metadata blocks).
- Enforces schema versions, permissions, and safety rules.
- Provides navigation metadata and feature flags.

### API Gateway
- Internal routing layer between UI-Service and platform services.
- Handles service discovery, internal auth, and routing.
- Not directly visible to the UI.

### Platform Services
- Domain-pure services (identity, membership, wallet, clans, events, progression, media, etc.).
- Expose canonical models only to the UI-Service and other internal services.
- Never exposed directly to the UI.

### UI Event Bus (Internal)
- UI-local event dispatcher for navigation events, modal events, and component-level interactions.
- Prevents direct component-to-component coupling.
- Scoped to the UI; not a global backend event bus.

---

## Behaviors / Rules

### UI–Backend Interaction Rules
- UI must only call the UI-Service.
- UI-Service must call platform services via the API Gateway.
- UI-Service must shape, sanitize, and version all responses before returning them to the UI.
- UI must treat UI-Service responses as the single source of truth.

### Layering Rules
- Layers are strictly ordered:
  - Background → Platform → Utility → Radial Wheel → Modals → System Alerts.
- Lower layers must not directly manipulate higher layers.
- Input is always captured by the topmost visible layer.
- Transitions between layers must be deterministic and defined (no ad-hoc cross-layer hacks).

### Navigation Rules
- Navigation uses a single global stack rooted at the Hub.
- Platforms and utilities push onto the same stack.
- Back button behavior is deterministic and stack-based.
- Navigation metadata (routes, labels, icons, visibility) is provided by the UI-Service.
- Navigation must not depend on hard-coded backend assumptions.

### Error & Fallback Rules
- All backend errors are normalized by the UI-Service into a small set of error types.
- UI must:
  - Show skeletons while loading.
  - Show placeholders when data is missing.
  - Show cached data when fresh data is unavailable.
  - Show clear, non-technical error states when requests fail.
- Partial failures must degrade gracefully (e.g., one carousel failing does not break the entire screen).

### Degradation Rules
- If data is slow: show skeletons and keep the UI interactive.
- If data is missing: show placeholders and allow navigation.
- If data is stale: show cached data with subtle indication if needed.
- If data fails: show fallback UI and allow retry where appropriate.

### Rendering Rules
- Rendering order is deterministic and consistent across sessions.
- Only components whose data changed should re-render.
- Long lists should use virtualization.
- Heavy computations must not run on the main UI thread.

---

## Workflows (Optional — not primary for this overview)
This document focuses on architecture rather than specific user workflows. Detailed workflows (e.g., navigation flows, modal flows) are defined in their respective planning docs (navigation_system, modal_system, etc.).

---

## States (Optional — high-level only)
- **Loading:** Data requested, skeletons visible.
- **Ready:** Data loaded and rendered.
- **Partial Ready:** Some data loaded, some failed or pending.
- **Error:** Data failed to load; fallback UI visible.
- **Empty:** Valid but empty state (no content, no events, etc.).

Detailed state machines are defined in system-specific docs.

---

## Data Model (Optional — UI-level contracts)
At the UI architecture level, we define **UI data contracts**, not full domain models.

- **Tile Contract:** id, title, subtitle, image, action, metadata, schemaVersion.
- **Carousel Contract:** id, title, list of tiles, layout hints, schemaVersion.
- **Navigation Node Contract:** id, label, icon, route, visibility rules, schemaVersion.
- **Background Contract:** id, image reference, platform association, schemaVersion.
- **Profile Block Contract:** displayName, avatar, membership tier, schemaVersion.

Canonical domain models live in platform service docs; the UI only sees shaped contracts from the UI-Service.

---

## API Surface (Optional — UI-Service perspective)
From the UI’s perspective, the primary API surfaces are:

- **GET /ui/hub**
  - Returns hub tiles, navigation metadata, and background metadata.
- **GET /ui/platform/{platformId}**
  - Returns platform tiles, platform metadata, and background metadata.
- **GET /ui/utility/{utilityId}**
  - Returns utility page content and metadata.
- **GET /ui/profile**
  - Returns profile block and membership entitlements.
- **GET /ui/navigation**
  - Returns global navigation metadata.
- **GET /ui/flags**
  - Returns feature flags relevant to the UI.

All responses include a `schemaVersion` and follow the UI data contracts.

---

## Safety Rules (Optional — summarized at architecture level)
- UI must never render arbitrary user-generated text where it can be abused.
- UI must rely on preset-only communication where applicable.
- UI-Service must enforce:
  - membership tier rules,
  - parental controls,
  - clan permissions,
  - creator permissions,
  - zero-moderation constraints.
- UI must not expose internal IDs, admin flags, or experimental fields.

---

## Performance Requirements

### Cold Path / Hot Path
- **Hot Path (must be fast, cached, and always available):**
  - Hub tiles
  - Platform tiles
  - Navigation metadata
  - Background metadata
  - Profile block
  - Membership entitlements
- **Cold Path (lazy-loaded):**
  - Deep platform pages
  - Utility pages
  - Modal content
  - Settings and secondary flows

### Render Budget
- Initial hub render: target < 200ms after data is available.
- Navigation transition: target < 100ms.
- Modal open: target < 80ms.
- Tile render: target < 16ms per frame.

### Asset Budget
- Background images: constrained to a defined max resolution and file size.
- Tile images: optimized and reused where possible.
- Icons: shared sprite sheets or icon fonts where appropriate.
- Fonts: limited number of font families and weights.

### Memory Budget
- Limit number of in-memory tiles per screen.
- Limit number of cached backgrounds.
- Limit number of cached platform pages.
- Evict least recently used UI data when memory thresholds are reached.

### Thread Budget
- Heavy work (parsing, image decoding, complex transforms) must not run on the main UI thread.
- UI-Service handles most shaping to reduce client-side computation.
- Background threads or worker contexts should be used where available.

### Minimal Re-Render Strategy
- Use stable keys for lists.
- Avoid re-rendering entire screens when only a subset changes.
- Memoize static or rarely changing components.
- Virtualize long lists and carousels.

---

## Observability / Telemetry (Optional)

- **Navigation Events:** screen views, platform entries, utility entries, back navigation.
- **Interaction Events:** tile clicks, radial wheel selections, modal opens/closes.
- **Error Events:** normalized error types, retries, fallbacks used.
- **Performance Metrics:** time-to-first-render, navigation latency, modal open time, cache hit/miss rates.
- **Telemetry Budget:**
  - Events must be batched where possible.
  - Avoid synchronous logging on critical paths.
  - Only essential events are logged to avoid overhead.

---

## Integration Points

- **UI ↔ UI-Service**
  - UI-Service is the only public API for the UI.
  - Provides shaped data, navigation metadata, feature flags, and schemaVersioned contracts.
  - Enforces security, permissions, and safety rules.

- **UI-Service ↔ API Gateway**
  - UI-Service calls platform services via the API Gateway.
  - Gateway handles routing, internal auth, and service discovery.
  - Platform services remain private and non-UI-aware.

- **UI ↔ Feature Flag System**
  - UI-Service injects feature flags into responses.
  - UI uses flags to gate features, layouts, and experiments.
  - Kill switches can disable features instantly.

- **UI ↔ Telemetry/Analytics**
  - UI sends structured events to telemetry endpoints.
  - UI-Service and platform services log correlated events for end-to-end tracing.

---

## Requirements / Standards

- UI must never call platform services directly.
- UI must treat UI-Service contracts as authoritative and versioned.
- UI must respect performance, asset, memory, and thread budgets.
- UI must follow strict layering and navigation rules.
- UI must use normalized error and fallback patterns.
- UI must not bypass feature flags or safety rules.
- UI must remain deterministic in behavior and rendering.

---

## Anti-Patterns

- UI calling platform services directly.
- UI depending on internal IDs or backend implementation details.
- Cross-layer hacks (e.g., modals directly manipulating platform state without going through defined flows).
- Multiple navigation stacks with inconsistent back behavior.
- Ad-hoc error handling and inconsistent fallback UI.
- Unbounded lists, unvirtualized carousels, or heavy components on critical paths.
- Logging or telemetry on every frame or every minor interaction.
- Ignoring schemaVersion or assuming backend shapes.

---

## Future Expansion

- **UI Rendering Pipeline:**
  - More detailed definition of render phases, batching, and scheduling.
- **UI State Machines:**
  - Formal state machines for navigation, modals, and key flows.
- **Predictive Prefetching:**
  - UI-Service prefetches likely-next data based on navigation patterns.
- **UI Idle Work Queue:**
  - Use idle time for cache warming, cleanup, and telemetry batching.
- **Animation System:**
  - Define animation budgets, allowed transitions, and motion guidelines.
- **Accessibility:**
  - Text scaling, high contrast modes, reduced motion, focus navigation, and screen reader support.
- **Multi-Surface Support:**
  - TV, desktop, mobile, and other surfaces sharing the same UI architecture and contracts.
- **Background & Platform Packs:**
  - Paid or unlockable background packs and platform theming, respecting asset and performance budgets.

