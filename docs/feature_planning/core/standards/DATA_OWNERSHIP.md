# DATA_OWNERSHIP

---

## 🎯 Purpose
Define authoritative ownership of all data types across EndlessGames to ensure consistency, safety, and deterministic behavior.

---

# 1. Ownership Principle
Every piece of data must have **one and only one** authoritative owner.

Derived data must be recomputable.  
Analytics is never a source of truth.

---

# 2. Ownership Model

| Data Type | Owner |
|----------|-------|
| Player Profile | Identity System |
| Identity Surfaces | Player Expression System |
| Preset Communication | Preset Communication System |
| Progression | Progression System |
| Quests | Quest System |
| Events | Event System |
| Inventory | Inventory System |
| Cosmetics | Cosmetics System |
| Currency | Economy System |
| Creator Content | Creator Ecosystem |
| SDK Experiences | EndlessCreator SDK |
| Media Content | Media Systems |
| Clan State | Clan System |
| Seasonal State | Seasonal Identity System |
| Hub Personalization | EndlessHub |
| Sessions | Session Orchestrator |

---

# 3. Rules
- No duplicate writes across systems.  
- No system may store another system’s authoritative data.  
- All cross‑system reads must be via defined interfaces.  
- All derived data must be traceable to its source.

---

# 4. Anti‑Patterns
- Shared mutable state  
- Implicit ownership  
- Cross‑system writes  
- Analytics‑driven state  

---