# PROMOTION RULES MODULE

## Overview
This module defines all selectable pawn promotion rules available during match creation. These rules apply across all board types.

---

## Promotion Options

### 1. Opposite Side Only
- Pawns promote only when reaching the far side of the board relative to their starting direction.
- Standard for 2-player and 4-player Single Board Mode.

---

### 2. Diagonal Opponents Only
- Pawns promote only when reaching the far side of the diagonal opponent.
- Useful for 4-player free-for-all.

---

### 3. Both Opposite + Diagonal
- Pawns may promote on either opposite or diagonal opponent’s side.
- Increases promotion frequency.

---

### 4. Multi-Promotion (3D Modes)
- Pawns promote each time they reach a valid promotion zone.
- Works well in Stacked, Cube, and Matrix modes.

---

### 5. Layer-Based Promotion
- Promotion occurs when reaching a specific layer (e.g., top or bottom board).
- Used in multi-board variants.

---

### 6. Region-Based Promotion
- Promotion occurs when entering an opponent’s “home region.”
- Useful for Cube and Matrix modes.

---

## Promotion Piece Options
Selectable:
- Queen  
- Rook  
- Bishop  
- Knight  
- Custom piece sets (future expansion)

---

## Notes
Promotion rules must be compatible with:
- Pawn movement mode  
- Board topology  
- Endgame mutation rules  

