# EndlessGames Unified Architecture

## Overview

EndlessGames is a multi-domain, event-driven, modular, and anti-exploit-first platform composed of interconnected systems and domains:

- Identity Layer
- Safety Layer
- Economy Layer
- Content Layer
- Social Layer
- Game Layer
- Platform Layer
- Data Layer

All systems are:
- Event-driven
- Stateless where possible
- Composable

---

## Core Layers & Domains

### Client Layer
- Browser-based interface
- Interacts with Game SDK and UI systems
- No trust placed in client data (client = untrusted)

### Game Layer
- Powered by Rule Template Library
- Responsible for generating gameplay events

### Event Layer
- Central system of record
- Stores all gameplay and interactions
- Append-only, immutable (events = verifiable truth)

### Processing Layer
- Consumes events and produces rewards, risk scores, and system state updates
- Includes Reward System, Risk System, Validation Pipelines

### Data Layer
- Stores users, sessions, rewards, risk profiles
- Split into transactional (OLTP), analytical (OLAP), and event log

### Control Layer
- Includes Configuration System and Feature Flag System
- Controls system behavior, rollout, and tuning

---

## Domains (Expanded)

**Identity:** Users, creators, roles

**Safety:** Constraints, enforcement

**Economy:** Value exchange

**Content:** Media and games

**Social:** Interactions

**Platform:** Orchestration

**Data:** Observability

---

## System Interaction Model

[User Action]
   ↓
[Domain System]
   ↓
[Event Emission]
   ↓
[Platform Layer]
   ↓
[Other Systems React]

---

## System Flow

Game → Events → Event Store → Processing Systems → Rewards / Risk → Data Storage → UI Feedback

---

## Core Systems

- Identity System
- Social System
- Game SDK
- Reward System
- Risk & Anti-Fraud System
- Permission System
- Configuration System
- Feature Flag System
- Event Registry
- Data Model

---

## Trust Model

- Client = untrusted
- Server = authoritative
- Events = verifiable truth

---

## Scaling Strategy

- Event partitioning by time
- Horizontal service scaling
- Stateless processing services
- Cached hot data

---

## Failure Strategy

- Event persistence guaranteed
- Processing is retryable
- Configs are rollback-safe
- Features are kill-switchable

---

## Core Principle

- No circular dependencies
- All dependencies must flow: Identity → Systems → Platform → Data
