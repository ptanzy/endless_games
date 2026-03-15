# CHESS — RUNTIME ARCHITECTURE

## Purpose
This document describes how the Chess runtime is structured, how engines interact, and how the game executes inside the EndlessGames platform.

---

## High‑Level Architecture

Match Config → Engine Initialization → Game Loop → UI Rendering → Telemetry → Endgame

---

## Engine Interaction Model

### 1. Match Creation Layer
- Reads rule modules
- Reads topology selection
- Produces `MatchConfiguration`
- Hands configuration to runtime

### 2. Initialization Layer
- Instantiates:
  - Movement Engine
  - Checkmate Engine
  - Turn Engine
  - Topology Engine
  - Piece Definition Layer
- Builds initial `GameState`

### 3. Game Loop Layer
- Receives input (player or AI)
- Validates via Movement Engine
- Resolves coordinates via Topology Engine
- Updates state
- Evaluates threats
- Applies rule modules
- Advances turn

### 4. Rendering Layer
- Renders board (2D, layered, cube, matrix)
- Renders pieces
- Renders overlays (threats, portals, terrain)
- Renders UI (turn order, timers, rule indicators)

### 5. Telemetry Layer
- Emits:
  - Move count
  - Turn duration
  - Match duration
  - Mode usage
  - Rule module usage
  - Player performance metrics

### 6. Endgame Layer
- Determines winner(s)
- Generates After‑Action data
- Triggers Moments
- Sends data to EndlessRank, EndlessPass, Events

---

## Determinism
Chess runtime is fully deterministic:

- No randomness  
- No hidden information  
- All engines pure except state updates  
- Replayable from move list  

---

## Extensibility
Chess supports:

- New modes  
- New rule modules  
- New topologies  
- New UI skins  
- New cosmetic surfaces  

All without modifying core engines.