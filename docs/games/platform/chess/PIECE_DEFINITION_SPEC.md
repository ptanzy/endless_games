# Piece Definition Specification

This document defines the properties and behaviors of chess pieces.# PIECE DEFINITION SPECIFICATION

## Overview
Defines all piece types, movement vectors, capture rules, and variant behaviors.

---

## Standard Pieces
### King
- 1-step in all directions  
- Optional 3D adjacency  
- Subject to bare king restrictions  

### Queen
- Full 2D or 3D vectors  

### Rook
- Orthogonal 2D or 3D  

### Bishop
- Diagonal 2D or 3D  

### Knight
- 2D L-jump  
- Optional 3D L-jump  

### Pawn
Movement modes:
- Classic forward  
- Forward + vertical  
- 3D forward vector  
- One-step queen  

Capture modes:
- Classic diagonal  
- Vertical diagonal  
- 3D diagonal  

---

## Variant Mechanics
### Decoration Rule
- Pieces gain movement abilities of captured pieces.

### Recruitment Rule
- Captured pieces switch allegiance.

### King Empowerment
- King gains additional movement in late game.

---

## Notes
Piece definitions must remain compatible with:
- Movement Engine  
- Promotion Rules  
- Terrain Rules  

