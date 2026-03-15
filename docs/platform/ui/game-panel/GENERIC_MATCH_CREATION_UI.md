# GENERIC MATCH CREATION UI

## Purpose
The Generic Match Creation UI provides a universal, game‑agnostic interface for configuring a match before it begins. Individual games extend this UI with their own rule modules, modes, and visual elements.

---

## Core Layout Structure

### 1. Header
- Game title
- Mode selector
- Back button
- Preset selector

### 2. Main Configuration Panel
Contains universal configuration blocks:

#### A. Player Configuration
- Player count
- Seat assignment
- Team selection
- AI toggles

#### B. Mode Configuration
- Game mode (e.g., Single Board, Double Board, etc.)
- Mode description
- Mode preview widget (game‑specific override)

#### C. Rule Modules
Universal rule module categories:
- Movement rules
- Promotion rules
- Elimination rules
- Turn order rules
- Team rules
- Advanced mechanics
- Terrain rules
- Portal rules
- Endgame mutation rules

Each game injects its own rule cards into these categories.

#### D. Presets
- Classic
- Competitive
- Chaos
- Custom presets (saved by user)

### 3. Summary Panel
- Selected mode
- Selected rules
- Player layout
- Estimated match length
- “Start Match” button

---

## Extension Points for Games
Each game may override or extend:

- Mode selector contents  
- Rule module cards  
- Mode preview widget  
- Game‑specific presets  
- Game‑specific warnings or constraints  

Example:
- Chess injects topology selectors (Single Board, Cube, Matrix)
- Checkers injects jump rules and kinging rules

---

## UX Goals
- Consistent across all games
- Modular and extensible
- Clear hierarchy of configuration
- Preview‑ready for any game type

