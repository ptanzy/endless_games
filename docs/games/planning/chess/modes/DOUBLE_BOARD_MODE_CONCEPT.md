# DOUBLE BOARD MODE — CONCEPT DOCUMENT

## Overview
Double Board Mode introduces two stacked boards (Top and Bottom), enabling vertical transitions and optional 3D movement. This mode is conceptual and not yet finalized.

---

## Board Architecture
- Two boards stacked vertically:
  - **Top Board:** East/West players
  - **Bottom Board:** North/South players

- Boards are aligned so that edge squares correspond vertically.

---

## Movement Rules
### 3D Movement Toggle
Selectable:
- **ON:** Full 3D vectors enabled  
- **OFF:** Only vertical transitions allowed  

### Vertical Movement
- Allowed only on aligned edge squares  
- Cost, blocking, and chaining rules are not yet finalized  

---

## Starting Positions
- Each player begins on their home board  
- No pieces start on the opposite board  

---

## Promotion Rules
Selectable:
- Classic (opposite side of home board)  
- Multi-promotion (each time a pawn reaches an opposite edge)  

---

## Checkmate Logic
- Cross-layer check/checkmate only if 3D movement is ON  
- Otherwise, checkmate is board-local  

---

## Open Questions
- Vertical movement cost  
- Whether vertical moves can be part of a longer move  
- Pawn vertical capture rules  
- Promotion on opposite board  
- Line-of-sight across layers  
- Edge alignment variants  

---

## Status
**Concept Only — Not Finalized**

