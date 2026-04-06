earn rewards
# EndlessGames Identity System

---

## Purpose
Defines how EndlessGames manages player identity, authentication, classification, and expression across all platform surfaces. Ensures every action is tied to a controlled, validated identity, and all identity features are safe, consistent, and enforceable.

---

## Core Concepts & Entities

- **User:** Real-world account holder
- **Account:** Platform-level identity
- **Session Identity:** In-session representation
- **Identity Surfaces:** Themes, frames, badges, seasonal, clan, creator identity
- **Account Types:**
  - Guest: No persistent identity, limited access, no data ownership, cannot earn/store rewards
  - Player: Persistent account, can earn rewards, form social connections, participate fully
  - Creator: Player with elevated permissions, can create games, monetize content, access creator systems
- **Age Classification:**
  - Child: Restricted interaction, can only interact with other child accounts, extra safety constraints
  - Adult: Broader access, still constrained by platform rules

---


## Identity Lifecycle
Guest → Registered Player → Verified Player → Creator (optional)

- **Guest Access:** Immediate, session-bound, no persistent storage
- **Registration:** Requires unique identifier (email or equivalent), age classification
- **Verification:**
  - Basic (account existence)
  - Age verification
  - Trust signals (behavioral)

---

## Components

- **Session Binding:** Identity must persist across gameplay sessions, media consumption, and social interactions.
  - *TBD: Session lifecycle and persistence rules are not explicitly defined in source docs.*
- **Role Model:**
  - Player: consumes content, plays games, interacts socially
  - Creator: uploads content, monetizes, participates in economy systems
  - *TBD: Explicit role definitions and boundaries are not consistently defined in source docs.*

---

---

## Identity Attributes
- user_id
- account_type
- age_group
- status (active, restricted, suspended, banned)
- trust_level (derived from behavior)
- risk_score

---

## Multi-Account Detection & Enforcement
- Link detection via device signals, behavior patterns, session overlap
- Link scoring: 0–49 (low), 50–69 (moderate), 70–84 (high), 85+ (critical)
- Enforcement: monitoring, reward reduction, restriction/lock based on score

---

## Event Model (from V3)
Minimum inferred events:
- user_created
- session_started
- session_ended
- role_assigned

*TBD: Event contracts are not formally defined in planning or feature docs.*

---

## Constraints & Rules
- One identity per actor (system enforced)
- No anonymous value extraction (guests cannot earn/store rewards)
- No identity switching exploits (rapid switching flagged)
- Identity must be consistent and atomic across all surfaces
- Identity surfaces are safe, cosmetic-only, and preset-reviewed
- No custom text, user-generated images/audio/themes
- No personal data displayed or exchanged
- All cross-system reads via defined interfaces; no direct mutation
- Ownership of identity is exclusive to the Identity System

*TBD: Permission enforcement layer is not explicitly defined in source docs.*

---

## Workflows

### 1. Account Creation & Authentication
1. User registers/authenticates
2. System creates/verifies account
3. Session identity established
4. Profile and identity surfaces initialized

### 2. Profile Customization
1. Player selects theme, frame, badge, or cosmetic (from reviewed presets)
2. Profile updates instantly and propagates to all surfaces
3. No unsafe content possible

### 3. Identity Change Workflow
1. Player requests identity change (theme, frame, etc.)
2. System validates request (preset-only, reviewed)
3. Change is atomic and consistent across all surfaces

### 4. Cross-System Identity Integration
1. Identity surfaces appear in social, creator, clan, and media systems
2. All integrations via defined interfaces; no direct data mutation
3. All integrations are observable and reversible

---

## Integration with Other Systems
- **Permission System:** Identity defines accessible actions
- **Reward System:** Rewards tied to user_id
- **Risk System:** Identity accumulates risk score
- **Social System:** Identity governs allowed interactions

---

## Observability
Track:
- Account creation rates
- Identity transitions
- Suspicious identity behavior
- Multi-account clusters

---

## Edge Cases
- Shared devices: Allowed but monitored, triggers link scoring
- Age misclassification: Flagged via behavioral inconsistencies
- Account recovery: Must preserve identity continuity, cannot reset risk history
- If a player attempts to use a non-reviewed/custom asset, system rejects change
- If a dependency system is unavailable, identity surfaces degrade safely
- If cross-system integration fails, identity reverts to last known safe state
- User switching roles (player → creator)
- Multiple sessions (if allowed)

*TBD: Concurrency rules and identity conflict resolution are not defined in source docs.*

---

## Enforcement Rules
- Identity violations increase risk score
- Severe violations restrict account capabilities

---

## System Interfaces
- Exposes: Account creation, authentication, profile management, identity surface selection APIs
- Consumes: Permissions Model, Data Ownership, Player Expression System, Seasonal Identity System
- All cross-system communication via events or API contracts; no shared mutable state

---

## Summary
The Identity System ensures every user is classified, constrained, and trackable; every action is attributable and enforceable. It is the foundation of safety, economy integrity, and anti-fraud systems.

---

## Source References
- /planning/platform/IDENTITY_SYSTEM.md
- /planning/social/PLAYER_EXPRESSION_SYSTEM_PLANNING.md
- /planning/platform/CROSS_PILLAR_INTEGRATION.md
- /planning/core/standards/DATA_OWNERSHIP.md
- /planning/core/standards/SYSTEM_BOUNDARIES.md
- /planning/core/doctrine/PLATFORM_DOCTRINE_OVERVIEW.md
- /planning/core/standards/PLATFORM_OWNERSHIP_MATRIX.md
- /planning/PLATFORM_DEPENDENCY_MAP.md
- /planning/PLANNING_OVERVIEW.md
