# PERMISSIONS_MODEL

---

## 🎯 Purpose
Define the complete role‑based access control (RBAC) model for EndlessGames, covering players, creators, clans, seasons, brands, platform staff, system actors, and membership‑based capability layers.

---

# 1. Player Roles

### Player
- Consume content  
- Participate in sessions  
- Equip cosmetics  
- Use presets  

### Clan Leader
- Manage clan identity  
- Approve members  
- Configure clan events  

### Clan Officer
- Assist leadership  
- Moderate clan activity  

### Seasonal Participant
- Engage in seasonal progression  
- Unlock seasonal rewards  

### Beta Tester
- Access feature‑flagged content  

---

# 2. Creator Roles (Tiered)

### Media Creator
- Upload videos  
- Publish Moments  
- Stream  

### Interactive Creator
- Build interactive content  
- Use Content‑Extension SDK  

### Game Creator
- Build games using Game SDK  

### Mode Creator
- Build modes inside EndlessGames titles  

### Creator Partner
- Access brand‑approved tools  
- Participate in sponsored events  

---

# 3. Platform Roles

### Admin
- Manage platform configuration  
- Approve content  
- Access moderation tools  

### Reviewer
- Review creator content  
- Review SDK experiences  

### Moderator
- Human‑in‑the‑loop safety checks  

### Support Agent
- Assist players  
- Resolve account issues  

### Brand Manager
- Manage brand integrations  

### Season Designer
- Configure seasonal arcs  

### Economy Designer
- Configure sinks/sources  

### Preset Curator
- Approve new presets  
- Manage preset categories  

---

# 4. System Roles (AI Actors)

### Validation AI
- Validate content  
- Enforce safety  

### Recommendation AI
- Rank Hub modules  
- Personalize feeds  

### SDK Safety AI
- Validate gameplay safety  

### Media Processing AI
- Process uploads  
- Extract clips  

---

# 5. Rules
- Least privilege  
- Explicit grants only  
- No implicit inheritance  
- All actions must be logged  
- AI cannot make irreversible decisions  

---

# 6. Anti‑Patterns
- Cross‑role elevation  
- Unbounded permissions  
- Tools bypassing RBAC  

---

# 7. Membership Tiers (Capability Layers)

Membership tiers **do not change roles**.  
They **add capabilities** on top of existing roles without granting authority.

Memberships expand *what* a user can do, not *who* they are.

---

## Basic Membership
- Standard presets  
- Standard identity surfaces  
- Standard Hub modules  
- Standard media consumption  
- Standard progression rate  
- Standard daily limits  

---

## Premium Membership
Adds to Basic:
- Premium presets  
- Premium identity surfaces  
- Premium Hub modules  
- Premium seasonal rewards  
- Increased daily limits  
- Faster soft‑currency earn rate  
- Access to premium media playlists  
- Access to premium clan boosts  

---

## Creator Membership
Adds to Creator Roles:
- Creator analytics  
- Creator monetization  
- Creator identity surfaces  
- Creator Hub modules  
- Creator media tools  
- Creator SDK access (tier‑gated)  
- Creator seasonal participation  

---

# 8. Membership Rules
- Memberships cannot grant admin, reviewer, or moderator authority  
- Memberships cannot bypass safety or validation  
- Memberships must be cosmetic‑only in impact  
- Memberships must be reversible and time‑bound  

---

# 9. Anti‑Patterns (Membership)
- Memberships granting gameplay advantages  
- Membership