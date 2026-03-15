# Game State and Turn Engine

This document details the management of game state and turn progression for chess.# GAME STATE AND TURN ENGINE

## Overview
This engine manages turn order, round structure, player elimination, and global game state transitions.

---

## Responsibilities
- Maintain active player list  
- Process turn order rules  
- Handle player elimination  
- Track rounds and cycles  
- Trigger endgame mutations  
- Manage timers  

---

## Turn Order Modes
- Clockwise  
- Counter-clockwise  
- Random each round  
- Host-defined order  

---

## Round Structure
- A round = all players take one turn  
- Randomization (if enabled) occurs between rounds  

---

## Player Elimination
Triggered when:
- King is captured  
- King is checkmated (if using instant elimination rules)  

Elimination behavior depends on selected module:
- Remove all pieces  
- Conquest (transfer pieces)  
- Freeze pieces  
- Neutral pieces  

---

## Game State Phases
1. **Setup**  
2. **Opening**  
3. **Midgame**  
4. **Endgame**  
5. **Mutation Phase** (optional)  
6. **Victory**  

---

## Endgame Mutation Triggers
- After X turns  
- After X minutes  
- After X rounds  

---

## Notes
This engine coordinates with:
- Movement Engine  
- Checkmate Engine  
- Match Creation Flow  

