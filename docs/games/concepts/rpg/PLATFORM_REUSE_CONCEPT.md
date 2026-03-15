# ♾️ ENDLESSGAMES — SHARED PLATFORM & REUSABLE SYSTEMS CONCEPT

## Purpose
This document defines how EndlessGames supports **multiple large-scale AI‑driven RPGs** using a **shared platform architecture**, **reusable UI components**, **common simulation layers**, and **unified AI systems**.  
The goal is to ensure that:

- The **Persistent AI‑Driven RPG**  
- The **Episodic AI‑Simulated RPG**

…can both run on the same foundation, minimizing duplication and maximizing scalability.

This document outlines the reusable layers, the extension points, and the architectural philosophy behind EndlessGames as a multi‑game ecosystem.

---

# 1. Platform Philosophy

EndlessGames is not a collection of separate games.  
It is a **single platform** with:

- Shared runtime  
- Shared UI library  
- Shared simulation engine  
- Shared AI orchestration  
- Shared media pipeline  
- Shared progression  
- Shared monetization  
- Shared developer tools  

Each game is a **module** that plugs into this platform.

This allows EndlessGames to scale to dozens of games without rewriting core systems.

---

# 2. Shared Runtime Layer

Both RPGs run on the same **EndlessGames Runtime**, which provides:

### Core Systems
- WebSocket networking  
- Player authentication  
- Character stats engine  
- Dice/roll engine  
- Combat resolution  
- Skill checks  
- Inventory system  
- Item definitions  
- Crafting system  
- Quest engine  
- Faction system  
- Economy system  
- Travel/pathfinding  
- World state management  
- Event logging  
- Telemetry  

### Why this matters
These systems are universal across RPGs.  
They should never be rewritten per game.

Each game simply **extends** or **configures** them.

---

# 3. Shared UI Component Library

EndlessGames uses a **unified UI component system** that all games inherit from.

### Shared UI Components
- Inventory UI  
- Character sheet  
- Dialogue UI  
- Quest log  
- Map UI  
- Skill tree  
- Combat log  
- Party UI  
- Faction reputation UI  
- Shop/trade UI  
- Crafting UI  
- Notifications  
- HUD elements  
- Tabs, lists, cards, panels  

### Game‑Specific Overrides
Each game can override:

- Themes  
- Icons  
- Layouts  
- Animations  
- Color palettes  
- Game‑specific widgets  

### Why this matters
You build the UI once.  
Every game benefits.

---

# 4. Shared Simulation Engine

Both RPGs use the same **simulation primitives**, even though they use them differently.

### Shared Simulation Features
- Time system (ticks, days, seasons)  
- NPC behavior trees  
- Faction AI  
- Economy simulation  
- Travel/pathfinding  
- Rumor system  
- Event triggers  
- Weather system  
- Monster spawning  
- Resource nodes  

### Game Differences
- **Persistent RPG:** simulation runs continuously in real time  
- **Episodic RPG:** simulation runs to generate story arcs  

### Why this matters
The simulation engine becomes a **platform service**, not a per‑game feature.

---

# 5. Shared AI Architecture

Both games use the same AI layers:

### Shared AI Modules
- Dialogue generator  
- Quest generator  
- Event narrator  
- Lore generator  
- Script writer (EndlessTube)  
- Rumor generator  
- Personality engine  
- Story arc generator  

### Game Differences
- **Persistent RPG