# PLATFORM LAYER

## Purpose
Acts as the orchestration layer connecting:
- Games
- Media
- Social
- Economy

---

## Responsibilities

### 1. Cross-System Events
- Trigger events across games/media/social
- Example:
  - Game win → reward → social post → feed boost

### 2. Unified Entry Points
- Home Hub
- Discovery feeds
- Event surfaces

### 3. Recommendation Engine
- Content ranking
- Game suggestions
- Creator promotion

---

## Event Model

All systems emit events:

Game:
- match_completed
- achievement_unlocked

Media:
- video_uploaded
- stream_started

Social:
- post_created
- interaction

Economy:
- reward_earned
- purchase_made

Platform layer:
- consumes all events
- redistributes intelligently

---

## Key Rule

No system talks directly to another system.

ALL communication goes through:
→ Platform Event Layer