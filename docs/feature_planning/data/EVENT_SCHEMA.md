# EVENT_SCHEMA

---

## 🎯 Purpose
Define the canonical structure for all platform events emitted across EndlessGames.

---

# 1. Event Structure
{
  event_name: string,
  actor_id: string,
  session_id: string,
  timestamp: ISO8601,
  metadata: object
}

---

# 2. Rules
- All systems must emit events  
- Events must be immutable  
- Event names must be consistent  
- Metadata must be structured and typed  
- Events must be observable and traceable  

---

# 3. Event Categories

### Gameplay Events
- player_joined_session  
- player_completed_game  

### Economy Events
- cosmetic_purchased  
- currency_earned  

### Progression Events
- quest_completed  
- level_up  

### Social Events
- preset_sent  
- reaction_added  

### Creator Events
- creator_published  
- creator_stream_started  

### SDK Events
- experience_started  
- game_completed  

### Media Events
- video_watched  
- clip_shared  

### Seasonal Events
- season_progressed  
- seasonal_reward_claimed  

---

# 4. Anti‑Patterns
- Free‑form metadata  
- Missing timestamps  
- Missing actor_id  
- Overloaded event names  

---
