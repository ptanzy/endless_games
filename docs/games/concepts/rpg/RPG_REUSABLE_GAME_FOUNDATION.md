# ♾️ ENDLESSGAMES — REUSABLE GAME FOUNDATION  
### (How Standalone Games Reuse RPG Systems)

## Purpose
This document explains how EndlessGames can support **multiple standalone games** that do *not* share worlds, lore, or timelines, while still reusing the majority of the RPG’s underlying systems. These games exist as independent titles in the EndlessGames launcher, but they all run on the same platform runtime, UI library, simulation primitives, and AI orchestration layer. This allows EndlessGames to expand into new genres with minimal additional engineering.

---

# 1. Standalone Game Overview
Standalone games built on the EndlessGames platform are **self‑contained experiences** with their own rules, settings, and progression loops. Examples include:

- Tactical Squad RPG  
- Colony Builder / Settlement Sim  
- Roguelike Dungeon Crawler  
- Card Battler / Deckbuilder  
- Detective / Mystery Generator  
- Monster Breeding Battler  
- City Builder / God Game  
- Automation / Factory Sim  
- Visual Novel / Relationship Sim  
- Gladiator Arena Battler  
- Space Exploration RPG  
- 4X‑Lite Civilization Sim  
- Puzzle RPG Hybrid  

These games do **not** connect to the Episodic or Persistent worlds.  
They simply reuse the platform’s shared systems to reduce development cost.

---

# 2. Reusable Components From the RPG

## 2.1 Combat Engine
The deterministic combat system is fully portable:
- hit/miss logic  
- damage formulas  
- status effects  
- abilities & cooldowns  
- turn order or real‑time resolution  
- combat logs  

Any standalone game with combat can reuse this engine with new animations or pacing.

---

## 2.2 Character Stats & Progression
The RPG’s stat framework can be reused across genres:
- attributes (STR, DEX, INT, etc.)  
- derived stats (HP, crit, resistances)  
- leveling curves  
- skill trees  
- equipment bonuses  

Standalone games can define their own classes or archetypes while using the same math.

---

## 2.3 Inventory & Item System
The RPG’s item architecture is universal:
- item definitions  
- rarity tiers  
- affixes/modifiers  
- equipment slots  
- consumables  
- crafting materials  

Only the theme changes (fantasy, sci‑fi, tactical, etc.).

---

## 2.4 AI Agents & Behavior
The AI layer supports:
- enemy decision‑making  
- ally support logic  
- boss behavior trees  
- scenario scripting  
- headless browser agents for automated testing  

This dramatically reduces development time for enemy encounters or NPC behavior.

---

## 2.5 UI Component Library
The shared UI system provides:
- inventory panels  
- character sheets  
- ability bars  
- tooltips  
- modal windows  
- list/grid components  
- map/minimap widgets  
- dialogue boxes  

Standalone games only need new styling and layout.

---

## 2.6 Simulation Primitives
Even without a full world, standalone games can reuse:
- time/tick system  
- event triggers  
- random encounter generator  
- loot tables  
- procedural map seeds  
- faction logic (optional)  

This supports roguelikes, tactical missions, colony sims, and more.

---

## 2.7 EndlessTube Integration
The same media pipeline can generate:
- mission recaps  
- battle highlights  
- colony history summaries  
- card spotlight videos  
- “season” or “chapter” summaries  

Standalone games still feed the platform’s content ecosystem.

---

# 3. Why This Works
The RPG provides a **general‑purpose fantasy/simulation engine**, not a single‑game codebase. By abstracting combat, stats, inventory, AI, UI, and simulation into reusable modules, EndlessGames can produce new standalone titles with:

- 70–90% shared code  
- 10–30% game‑specific logic  
- minimal duplication  
- consistent UX  
- unified monetization  
- unified progression  
- unified media output  

This is the foundation of a **multi‑title platform**, not a one‑off game.

---

# 4. Summary
Standalone EndlessGames titles can reuse the RPG’s:
- combat  
- stats  
- inventory  
- AI  
- UI  
- simulation  
- event engine  
- EndlessTube pipeline  

…while delivering completely independent experiences with their own worlds, rules, and identities. This approach allows EndlessGames to scale into a diverse catalog of games without fragmenting the codebase or inflating documentation.

