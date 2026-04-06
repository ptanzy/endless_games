# GENERIC AFTER ACTION SCREEN

## Purpose
The Generic After‑Action Screen provides a universal results interface after a match ends. It displays winners, standings, stats, and rewards. Each game may inject its own stat modules.

---

## Core Layout Structure

### 1. Header
- “Match Results”
- Mode name
- Match duration

### 2. Winner Panel
- Winner(s)
- Team victory indicator (if applicable)
- Highlighted avatars

### 3. Standings Panel
For each player:
- Placement (1st, 2nd, 3rd, 4th)
- Avatar
- Name
- Team
- Status (eliminated, survived, surrendered)

### 4. Stats Panel
Universal stats:
- Turns taken
- Moves made
- Time spent
- Captures (if applicable)
- Damage dealt (for RPGs)
- Score (if applicable)

### 5. Timeline Panel
- Key events
- Eliminations
- Promotions
- Terrain changes
- Portal activations

### 6. Rewards Panel
- XP
- Currency
- Unlocks

### 7. Footer
- Rematch
- Return to Lobby
- Exit to Games Panel

---

## Extension Points for Games
Games may override:

- Stat modules (e.g., Chess: piece value captured)
- Timeline events
- Reward logic
- Visual themes

---

## UX Goals
- Celebrate victory
- Provide meaningful stats
- Encourage replay
- Maintain platform consistency

