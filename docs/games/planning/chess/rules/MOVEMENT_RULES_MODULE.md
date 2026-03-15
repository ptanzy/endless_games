# MOVEMENT RULES MODULE

## Overview
This module defines all selectable movement-related rules available during match creation. These rules apply across all board architectures (Single Board, Stacked Boards, Cube, Matrix, etc.) unless otherwise noted.

---

## Movement Mode Options

### 1. Standard 2D Movement
- Pieces move exactly as in classic chess.
- No vertical or 3D movement allowed.
- Used for Single Board Mode and as a fallback for variants.

---

### 2. Vertical-Only Movement
- Pieces may move between layers only through aligned vertical squares.
- No diagonal or 3D vector movement.
- Vertical transitions count as a single move unless otherwise specified.

---

### 3. Full 3D Vector Movement
- Enables full 3D movement across x, y, and z axes.
- Applies to:
  - Rooks (orthogonal 3D)
  - Bishops (diagonal 3D)
  - Queens (full 3D)
  - Knights (3D L-jumps)
- Kings gain 3D adjacency movement.
- Pawns require special rules (see Pawn Movement section).

---

## Pawn Movement Options

### 1. Classic Forward-Only
- Pawns move forward in 2D only.
- No vertical movement unless explicitly allowed.

### 2. Forward + Vertical
- Pawns may move forward or ascend/descend vertically.
- Captures may include vertical diagonals.

### 3. 3D Forward Vector
- Forward direction is defined as a 3D vector.
- Pawns may move along that vector in any axis combination.

### 4. One-Step Queen Movement
- Pawns move like a queen but only one square.
- Simplifies 3D pawn logic for Matrix Mode.

---

## Knight Movement Options

### 1. 2D Knight
- Standard L-shaped movement.

### 2. 3D Knight
- Moves in any L-shape across 3D:
  - (2,1,0), (2,0,1), (1,2,0), (1,0,2), (0,2,1), (0,1,2)

---

## Line-of-Sight Rules

### 1. 2D Line-of-Sight Only
- Blocking applies only on the current layer.

### 2. Full 3D Line-of-Sight
- Blocking applies across all axes.
- Required for Cube and Matrix modes.

---

## Vertical Movement Cost Options

### 1. Normal Move
- Vertical transitions cost 1 move.

### 2. Double Move
- Vertical transitions cost 2 moves (slower vertical play).

### 3. Free Vertical Movement
- Vertical transitions cost 0 movement (rare, chaotic mode).

---

## Notes
Movement rules interact heavily with:
- Promotion rules  
- Terrain rules  
- Portal rules  
- Endgame mutation rules  

This module is foundational to all 3D variants.

