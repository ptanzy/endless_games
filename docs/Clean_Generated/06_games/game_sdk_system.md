IDENTITY & ACCOUNT SYSTEM (V3)
1. Purpose

The Identity & Account System defines:

how users are created and identified
how accounts evolve over time
how roles are assigned
how safety constraints (especially age) are enforced

This system ensures:

Every action is tied to a controlled identity with enforceable permissions and lifecycle constraints

2. Core Principles
2.1 Identity Required for Control
all meaningful actions require:
a persistent identity
2.2 Guest Isolation
guests exist for:
frictionless entry
but are:
heavily restricted
non-persistent
2.3 Age-Based Safety Enforcement
age classification is:
mandatory
enforced system-wide
2.4 Single Source of Truth
identity system is:
authoritative for:
roles
age
permissions
3. Account Types
3.1 Guest Account
Definition
Temporary, non-persistent user
Capabilities
play games (limited)
Restrictions
no:
data storage
friendships
messaging
rewards
content creation
Lifecycle
Guest → (upgrade) → Player
3.2 Player Account
Definition
Persistent user identity
Capabilities
full participation in:
social systems
rewards
gameplay
Requirements
account creation
age classification
3.3 Creator Account (Role-Based)
Definition
not a separate account
a role assigned to Player
Requirements
meet eligibility criteria
approval process
4. Account Lifecycle
4.1 Creation
User enters platform →
  Guest created →
    Optional upgrade to Player
4.2 Upgrade Flow (Guest → Player)
Requirements
create account credentials
provide age information
Result
Guest → Player
4.3 Role Assignment
Player →
  meets criteria →
    applies →
      approved →
        Creator role assigned
4.4 Account Persistence
Player accounts:
store:
progress
rewards
relationships
4.5 Deactivation (Future)

⚠️ Required:

[ FUTURE SPEC ]
Account suspension / deactivation rules
5. Identity Model
5.1 Unique User ID

Each user has:

UserID (immutable)
5.2 Identity Attributes

Stored attributes:

Age Classification
Roles
Account State
Risk Score (from observability)
5.3 No Anonymous Actions
all actions must be:
tied to UserID
6. Age Classification System (CRITICAL)
6.1 Age Groups
Child
Non-Child
6.2 Enforcement

Age classification controls:

friendships
messaging
monetization exposure
6.3 Hard Constraints
Child ↔ Adult interaction = NOT allowed
6.4 Immutability
age classification:
cannot be freely changed

⚠️ Future spec needed:

Age verification method
7. Role System Integration
7.1 Role Assignment

Roles include:

Player
Creator
Clan Officer
Clan Leader
7.2 Multi-Role Support
users can have:
multiple roles simultaneously
7.3 Role Source

Roles assigned by:

system rules
clan system
approval workflows
8. Authentication (High-Level)
8.1 Required for Player Accounts
secure login system
8.2 Session Management
each session tied to:
UserID

⚠️ Not deeply specified (implementation layer)

9. Permissions Integration
9.1 Identity as Root

Permissions depend on:

UserID + Roles + Age + Risk Score
9.2 Dynamic Adjustment
permissions change based on:
behavior
risk
10. Observability Integration
10.1 Identity Tracking

Track:

account creation
upgrades
role changes
10.2 Risk Score Attachment

Each identity has:

Risk Score

Used for:

enforcement
reward validation
11. Economy Integration
11.1 Reward Eligibility
only Player accounts can:
earn rewards
11.2 Guest Restriction
guests:
cannot accumulate value
11.3 Creator Earnings
tied to:
identity
role
12. Constraints
12.1 One Identity Per User (Intent)
system should discourage:
multiple accounts
12.2 No Anonymous Persistence
no stored value without identity
12.3 No Age Bypass
age rules cannot be overridden
13. Missing / Future Specs
13.1 Age Verification System
how age is confirmed
13.2 Multi-Account Detection
anti-alt account system
13.3 Account Recovery
password reset
recovery flows
13.4 Account Suspension / Ban Logic
enforcement rules