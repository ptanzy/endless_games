# CHESS MATCH LOBBY — UI EXTENSIONS

## Purpose
This document defines chess-specific UI elements that extend the Generic Match Lobby. These extensions provide topology previews, rule summaries, and team layout logic unique to chess.

---

## Extension Areas

### 1. Chess Board Preview
The preview panel displays:
- Selected topology (Single, Stacked, Cube, Matrix, etc.)
- Board orientation
- Player seat positions
- Team colors
- Layer indicators (for multi-board modes)

Modes supported:
- 2D board preview
- Layered board preview
- Cube face preview
- Matrix voxel preview

---

### 2. Chess Rule Summary Formatting
Chess overrides the generic rule summary to highlight:
- Movement mode (2D, vertical, 3D)
- Promotion rules
- Elimination behavior
- Terrain/portal presence
- Endgame mutation triggers

---

### 3. Team Layout Logic
Chess-specific team logic:
- N+W vs S+E (default)
- Custom team assignment (if enabled)
- Team color indicators on preview board

---

### 4. Player Seat Visualization
Chess adds:
- Seat compass (N, E, S, W)
- Seat-based board rotation preview
- Seat conflict warnings (e.g., “Two players assigned to North”)

---

### 5. Chess Lobby Tips
Examples:
- “Teammates cannot check each other.”
- “Vertical movement is enabled in this mode.”
- “Promotion rules: Opposite + Diagonal.”

---

## UX Goals
- Provide clarity for complex topologies
- Make team layout intuitive
- Ensure players understand rule interactions before starting

