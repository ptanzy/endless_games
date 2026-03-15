# CHESS MATCH CREATION — UI EXTENSIONS

## Purpose
This document defines all chess-specific UI extensions that plug into the Generic Match Creation UI. These extensions add chess modes, rule modules, topology selectors, and visual previews.

---

## Extension Areas

### 1. Mode Selector Extensions
Chess injects the following modes into the generic mode selector:

- Single Board Mode (8×8 or 10×10)
- Double Board Mode
- Triple Board Mode
- Cube Mode
- Matrix Mode (8×8×8 or 10×10×10)
- Fan-Fold Mode
- Torus Mode

Each mode includes:
- Description
- Complexity rating
- Visual preview
- Recommended presets

---

### 2. Chess Rule Module Cards
Chess adds its own rule cards to the generic rule module categories:

#### Movement Rules
- 2D Classic Movement
- Vertical Movement (Stacked Modes)
- Full 3D Movement (Cube/Matrix)
- 3D Knight Jumps

#### Promotion Rules
- Opposite Side Only
- Diagonal Opponent Only
- Both Opposite + Diagonal
- Multi-Promotion (3D Modes)
- Layer-Based Promotion

#### Elimination Rules
- Remove All Pieces
- Conquest Mode
- Freeze Pieces
- Neutral Pieces

#### Team Rules
- No Friendly Check
- No Pass-Through
- Shared Victory
- Limited Communication

#### Advanced Mechanics
- Decoration Rule
- Recruitment Rule
- Bare King Restrictions
- Forced Aggression
- Fog of War

#### Terrain Rules
- Collapsing Squares
- Rising Platforms
- Rotating Sections
- Dangerous Tiles

#### Portal Rules
- Paired Portals
- Random Portals
- Shifting Portals
- Capture Through Portal

#### Endgame Mutations
- Sudden Death
- Accelerated Promotion
- Shrinking Board
- Forced Aggression
- Fog of War Activation
- King Empowerment

---

### 3. Chess Topology Selector
A dedicated panel appears when selecting a chess mode:

- Board size (8×8, 10×10)
- Layer count (1, 2, 3)
- Cube face configuration
- Matrix dimensions
- Fan-fold hinge direction
- Torus wrap direction

---

### 4. Chess Board Preview Widget
A dynamic preview that updates based on:
- Mode
- Topology
- Rule modules
- Player count

Supports:
- 2D preview
- Layered preview
- Cube preview
- Matrix voxel preview

---

### 5. Chess Presets
Chess injects presets into the generic preset selector:

- Classic Chess
- 4-Player Standard
- 3D Chess (Stacked)
- Cube Chess
- Matrix Chess
- Chaos Chess
- Hardcore Chess

---

## UX Goals
- Make complex chess variants approachable
- Provide visual clarity for 3D modes
- Keep rule selection modular and intuitive

