# SINGLE BOARD MODE — PLANNING DOCUMENT

## Overview
Single Board Mode is the foundational mode of the 3D Chess Platform. It represents the classic 2D chess experience extended to support 2–4 players, optional teams, and a modular rule system. This mode is fully finalized and serves as the baseline for all other variants.

---

## Board Configuration
### Board Size
- **2 players:** 8×8 board  
- **4 players:** 10×10 board  

### Player Count
- Supports **2–4 players**

### Team Options
Selectable at match creation:
- **Free-for-All**
- **Teams:** North + West vs South + East  
  - Teammates do not check or checkmate each other  
  - Teammates cannot pass through each other’s pieces  
  - Teammates win together  

---

## Piece Set
- Standard chess set per player  
- No special or variant pieces in this mode  

---

## Win Conditions
Selectable at match creation:
- Last king standing  
- Team victory  
- First checkmate wins (speed mode)  
- Point-based elimination (future option)  

---

## Elimination Behavior
Selectable at match creation:

### Option A — Remove All Pieces  
When a king is captured, all of that player’s pieces are removed from the board.

### Option B — Conquest Mode  
When a king is captured, all of that player’s pieces immediately transfer to the capturing player.

---

## Promotion Rules
Selectable at match creation:
- **Opposite Side Only**
- **Diagonal Opponents Only**
- **Both Opposite + Diagonal**

---

## Checkmate Logic
Uses **standard 4-player chess rules**:
- A player is eliminated when their king is captured  
- Checkmate does not end the game  
- Multiple players may be in check  
- Eliminated players cannot move  
- Their pieces behave according to the selected elimination rule  

---

## Draw Logic
Selectable or default:
- Stalemate = draw  
- Repetition = draw  
- Insufficient material = draw  
- Time-based draw  
- Mutual agreement draw (via preset chat wheel)  

---

## Turn Order
Selectable at match creation:
- **Clockwise**
- **Counter-clockwise**
- **Random Each Round** (turn order reshuffles every full cycle)

---

## Setup Diagrams
(To be added in a future visual documentation pass.)

---

## Notes
Single Board Mode is the only fully finalized mode and acts as the baseline for engine validation, UI testing, and rule module integration.

