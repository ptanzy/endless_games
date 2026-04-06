DATA MODEL SPEC (V3)
1. Purpose

The Data Model defines:

core entities
relationships between systems
storage structure
data ownership

This ensures:

All systems operate on a consistent, scalable, and queryable data foundation

2. Core Principles
2.1 Event-Driven Source of Truth
events are:
immutable
append-only
2.2 Derived State
most system state is:
derived from events
2.3 Separation of Concerns
split into:
transactional data
analytical data
2.4 Ownership Boundaries
each system owns:
its data
3. Core Entities
🧍 3.1 USER
{
  "user_id": "uuid",
  "account_type": "guest | player | creator",
  "age_group": "child | adult",
  "status": "active | restricted | banned",
  "created_at": "timestamp"
}
🔐 3.2 USER_ROLES
{
  "user_id": "uuid",
  "roles": ["player", "creator", "clan_leader"]
}
👥 3.3 FRIENDSHIP
{
  "user_id": "uuid",
  "friend_id": "uuid",
  "status": "pending | accepted | blocked",
  "created_at": "timestamp"
}
🛡️ 3.4 CLAN
{
  "clan_id": "uuid",
  "name": "string",
  "created_by": "user_id",
  "created_at": "timestamp"
}
👥 3.5 CLAN_MEMBERSHIP
{
  "clan_id": "uuid",
  "user_id": "uuid",
  "role": "member | officer | leader",
  "joined_at": "timestamp"
}
🎮 3.6 GAME
{
  "game_id": "uuid",
  "creator_id": "user_id",
  "game_type": "string",
  "version": "string",
  "status": "pending | approved | rejected"
}
🎯 3.7 GAME_SESSION
{
  "session_id": "uuid",
  "game_id": "uuid",
  "player_ids": ["user_id"],
  "start_time": "timestamp",
  "end_time": "timestamp",
  "result": "win | loss | draw"
}
⚡ 3.8 EVENT (CORE)
{
  "event_id": "uuid",
  "event_type": "string",
  "version": "string",
  "actor_id": "user_id",
  "session_id": "uuid",
  "timestamp": "timestamp",
  "payload": {}
}
💰 3.9 REWARD
{
  "reward_id": "uuid",
  "user_id": "uuid",
  "session_id": "uuid",
  "value": "number",
  "coin": "number",
  "gold": "number",
  "reward": "number",
  "created_at": "timestamp"
}
💸 3.10 CASHOUT
{
  "cashout_id": "uuid",
  "user_id": "uuid",
  "amount": "number",
  "status": "pending | approved | rejected",
  "created_at": "timestamp"
}
👁️ 3.11 RISK_PROFILE
{
  "user_id": "uuid",
  "risk_score": "number",
  "last_updated": "timestamp"
}
🔗 3.12 ACCOUNT_LINK (Multi-Account)
{
  "user_id_a": "uuid",
  "user_id_b": "uuid",
  "link_score": "number",
  "last_updated": "timestamp"
}
⚙️ 3.13 CONFIG
{
  "config_key": "string",
  "value": "any",
  "version": "string",
  "updated_at": "timestamp"
}
🎯 4. RELATIONSHIPS
Core Graph
USER
 ├── USER_ROLES
 ├── FRIENDSHIP
 ├── CLAN_MEMBERSHIP → CLAN
 ├── GAME (creator)
 ├── GAME_SESSION
 │     └── EVENT
 │           └── REWARD
 ├── CASHOUT
 ├── RISK_PROFILE
 └── ACCOUNT_LINK
Key Relationships
User → Game
one creator → many games
Game → Session
one game → many sessions
Session → Event
one session → many events
Event → Reward
events → reward calculation
User ↔ User
friendship
account linking
🧠 5. DATA LAYERS
5.1 Transactional Layer (OLTP)

Stores:

users
sessions
rewards
cashouts
5.2 Event Layer (Event Log)

Stores:

all events (append-only)
5.3 Analytical Layer (OLAP)

Derived:

aggregates
risk metrics
economy metrics
🔄 6. DATA FLOW
Game →
  Events →
    Event Store →
      Reward System →
        Reward Table →
          Risk System →
            Risk Profile
🔐 7. DATA OWNERSHIP
System	Owns
Identity	USER
Social	FRIENDSHIP, CLAN
Games	GAME, SESSION
Events	EVENT
Economy	REWARD, CASHOUT
Observability	RISK_PROFILE, ACCOUNT_LINK
Config	CONFIG
⚡ 8. PERFORMANCE STRATEGY
Indexing
user_id
session_id
event_type
Partitioning
events partitioned by:
time
Caching
hot data:
sessions
risk scores
🔁 9. CONSISTENCY MODEL
Strong Consistency
cashout
reward writes
Eventual Consistency
analytics
risk updates
🚨 10. CONSTRAINTS
10.1 No Direct State Mutation
systems must:
rely on events
10.2 No Orphan Data
all records must:
link to user/session
10.3 Immutable Event Store
cannot edit/delete events
🟡 11. OPEN DECISIONS
Storage Technology
SQL vs NoSQL vs hybrid
Event Processing Mode
streaming vs batch
Data Retention Policies
per entity
🚨 CRITICAL IMPACT
1. Enables Implementation
engineers now know:
what to build
2. Connects All Systems
identity → games → economy → fraud
3. Supports Scale
event-driven + partitioned