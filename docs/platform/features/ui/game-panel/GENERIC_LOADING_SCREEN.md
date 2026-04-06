# GENERIC LOADING SCREEN

## Purpose
The Generic Loading Screen provides a unified loading experience across all games. It displays progress, player avatars, rule summaries, and game‑specific tips.

---

## Core Layout Structure

### 1. Background
- Game‑agnostic default background
- Game‑specific override allowed

### 2. Loading Panel
- Progress bar
- Loading percentage
- Current loading step (e.g., “Initializing Board Topology”)

### 3. Player Section
- Player avatars
- Seat positions
- Connection status indicators

### 4. Rule Summary
- Mode name
- Key rule modules
- Special mechanics enabled

### 5. Tips Section
- Rotating tips
- Game‑specific tip bank

---

## Extension Points for Games
Games may override:

- Background art
- Tip bank
- Loading steps (e.g., “Generating Map Seed” for RPGs)
- Preview animations

---

## UX Goals
- Smooth transition from lobby to gameplay
- Clear loading progress
- Reinforce rules and mode context
- Maintain consistent platform identity

