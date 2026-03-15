# Checkmate and Draw Engine

This document describes the logic and rules for determining checkmate and draw conditions in chess.# CHECKMATE AND DRAW ENGINE

## Overview
This engine determines check, checkmate, stalemate, and draw conditions across all board types and rule modules.

---

## Responsibilities
- Detect check and checkmate  
- Detect stalemate  
- Detect draw conditions  
- Handle multi-player and team logic  
- Support 3D threat detection  
- Integrate elimination rules  

---

## Check Detection
### 1. Threat Mapping
- For each enemy piece, generate all legal attack squares.
- Supports:
  - 2D threat maps  
  - 3D threat maps  
  - Portal-enabled threats  
  - Terrain-modified threats  

### 2. King Position Validation
- Determine if king is in a threatened square.
- Multi-layer and 3D adjacency supported.

---

## Checkmate Logic
Uses standard 4-player chess rules:
- King is in check  
- No legal moves to escape  
- No allied piece can block or capture the threat  
- Player is eliminated  

---

## Stalemate Logic
- King is not in check  
- No legal moves available  
- Behavior depends on selected draw rules  

---

## Draw Conditions
Selectable:
- Stalemate = draw  
- Repetition = draw  
- Insufficient material  
- Time-based draw  
- Mutual agreement  

---

## Team Logic
- Teammates cannot check each other  
- Shared victory  
- Shared elimination (optional future rule)  

---

## 3D Threat Detection
- Full 3D line-of-sight  
- Vertical threats  
- Diagonal 3D threats  
- Knight 3D jumps  

---

## Notes
This engine must remain topology-aware and rule-module-aware.

