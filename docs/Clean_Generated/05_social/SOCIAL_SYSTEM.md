# Social System

## 1. Purpose

The Social System defines:

- how users connect
- how they interact
- what interactions are allowed

This system ensures:

> All social behavior is safe, constrained, and non-exploitable.

---

## 2. Core Principles

---

### 2.1 Restricted Interaction Model

- users cannot freely communicate  
- all interactions must be:
  - predefined
  - system-controlled  

---

### 2.2 Safety by Design

- unsafe communication is:
  - impossible, not moderated  

---

### 2.3 Relationship-Gated Interaction

- interaction requires:
  - explicit relationship (e.g., friendship)  

---

### 2.4 Anti-Exploitation

- social systems must not:
  - enable reward farming  
  - enable collusion  

---

## 3. Core Components

# 👥 3.1 Friendship System

## 3.1.1 Friendship States

none
pending
accepted
blocked
3.1.2 Rules
users must:

send request → accept → become friends

only friends can:

interact in games

send messages

3.1.3 Constraints
rate-limited requests

max friend count enforced

duplicate requests prevented

3.1.4 Safety Rules
child accounts:

can only friend:

other child accounts

💬 3.2 Interaction System
3.2.1 Allowed Interactions
Users can only send:

predefined messages
system-generated invites
structured signals
3.2.2 Example Messages
“Invite to play this game”

“Join my clan”

“Play again?”

3.2.3 Forbidden
free text input

external contact requests

off-platform communication

3.2.4 Interaction Constraints
only between:

friends

🛡️ 3.3 Interaction Enforcement
3.3.1 Age-Based Restrictions
child ↔ adult interaction:

blocked

3.3.2 Risk-Based Restrictions
high-risk users:

limited or blocked interaction

3.3.3 Permission-Based Restrictions
interactions must pass:

permission checks

🧑‍🤝‍🧑 3.4 Clan System
3.4.1 Purpose
enable structured group play

support coordinated gameplay

3.4.2 Clan Structure
Clan
 ├── Leader
 ├── Officers
 └── Members
3.4.3 Roles
Leader:

full control

Officer:

manage members

Member:

participate

3.4.4 Rules
users must:

be invited or approved

clan size:

capped

3.4.5 Constraints
membership limits

rate-limited joining/leaving

no rapid switching between clans

3.4.6 Anti-Exploit Constraints
detect:

repeated internal reward loops

enforce:

diversity of interaction

🔄 3.5 Interaction Graph Constraints
3.5.1 Repetition Limits
repeated interaction with same user:

reduces reward value

3.5.2 Diversity Requirement
users must:

interact with multiple users

3.5.3 Cluster Detection
tight interaction groups:

flagged for review

4. Data Model Integration
Friendship → USER ↔ USER

Clan → CLAN + MEMBERSHIP

Interaction → Event System

5. Event Integration
Events include:

friendship.requested

friendship.accepted

clan.joined

interaction.blocked

6. Observability
Track:

friend graph density

interaction frequency

repeated pair interactions

clan activity patterns

7. Enforcement
7.1 Soft Enforcement
reduce rewards for:

repetitive interactions

7.2 Medium Enforcement
limit:

interactions

clan participation

7.3 Hard Enforcement
block:

interaction capabilities

8. Edge Cases
8.1 Sparse Networks
new users:

allowed more flexibility

8.2 High-Trust Users
may receive:

relaxed limits

8.3 Clan Abuse
clans used for farming:

penalized

9. Open Decisions
friend count limits

clan size limits

interaction frequency caps

SUMMARY
The Social System ensures:

all interaction is:

controlled

safe

non-exploitable

relationships are:

explicit

constrained

communication is:

structured

safe by design

This system is critical for:

child safety

fraud prevention

long-term platform integrity
