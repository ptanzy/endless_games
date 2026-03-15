# GENERIC MATCH LOBBY

## Purpose
The Generic Match Lobby is the universal waiting room before a match begins. It handles player readiness, team assignment, rule review, and host controls. Each game may extend the preview area or add game‑specific lobby widgets.

---

## Core Layout Structure

### 1. Header
- Match name
- Host indicator
- Back/Exit button

### 2. Player List Panel
For each player:
- Avatar
- Name
- Seat (N, E, S, W)
- Team color
- Ready indicator
- AI badge (if applicable)

Host controls:
- Kick player
- Swap seats
- Assign teams

### 3. Game Preview Panel
- Board/map preview (game‑specific)
- Mode description
- Rule summary
- Topology preview (if applicable)

### 4. Chat / Communication
- Preset chat wheel
- Quick messages
- No free‑text chat (platform rule)

### 5. Footer
- Host: “Start Match”
- Players: “Ready / Not Ready”

---

## Extension Points for Games
Games may override:

- Preview widget (e.g., Chess shows board topology)
- Rule summary formatting
- Team layout logic
- Additional lobby widgets (e.g., deck preview for card games)

---

## UX Goals
- Clear readiness state
- Transparent rule summary
- Predictable host controls
- Consistent across all games

