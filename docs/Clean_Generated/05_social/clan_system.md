FRIENDSHIP SYSTEM SPEC (V3)
1. Purpose

The Friendship System defines:

how users form connections
how relationships are validated
how interaction eligibility is determined

This system ensures:

All interactions are based on intentional, mutual relationships and cannot be exploited at scale

2. Core Principles
2.1 Mutual Consent Only
friendships require:
request + acceptance
no unilateral relationships
2.2 No Passive Networks
no:
followers
subscribers
one-way connections
2.3 Friction by Design
forming relationships must require effort
prevents:
bot networks
mass farming
2.4 Safety First
relationships must respect:
age segmentation
system restrictions
3. Friendship Lifecycle
3.1 States
None → Requested → Accepted → Active → Removed
3.2 Flow
User A sends request →
User B receives request →
User B accepts →
Friendship becomes active
3.3 Removal
either user can:
remove friendship

Effect:

Active → Removed → No Interaction Allowed
4. Friendship Creation Constraints
4.1 Request Limits

To prevent spam:

max outgoing requests per:
hour
day
4.2 Acceptance Limits
max new friendships per:
day
4.3 Total Friend Cap

Each user has:

Max Friends Limit (system-defined)

⚠️ Missing (tunable later):

Exact caps must be defined based on testing
5. Discovery Model (CRITICAL)
5.1 No Open Discovery

Users cannot:

browse random users
search globally without constraint
5.2 Allowed Discovery Paths

Friend discovery is limited to:

- Recent gameplay participants
- Clan members
- Existing friend-of-friend (optional, controlled)
5.3 No External Import
cannot import:
contacts
social graphs
Result

Prevents mass friend graph construction by bots

6. Child Safety Integration
6.1 Age-Based Constraint
Child ↔ Child → Allowed
Child ↔ Adult → NOT allowed
6.2 Enforcement
friend request blocked if:
age groups mismatch
6.3 No Override
no exceptions
no manual bypass
7. Interaction Eligibility
7.1 Core Rule
Interaction allowed ONLY IF:
  Friendship = Active
7.2 Immediate Effect
removing friendship:
instantly removes:
messaging
gameplay interaction eligibility
8. Anti-Exploitation Controls
8.1 Rapid Network Growth Detection

Detect:

User creates many friendships quickly

→ trigger restrictions

8.2 Low-Quality Connection Detection

Signals:

no gameplay interaction
repeated shallow connections

→ reduce validity

8.3 Friendship Farming Prevention

Patterns like:

Create friend → interact → remove → repeat

→ invalidated for rewards

9. Friendship Quality Model (IMPORTANT)
9.1 Relationship Strength (Implicit Metric)

Friendships are evaluated based on:

gameplay interaction
engagement frequency
diversity of interaction
9.2 Impact
stronger friendships:
higher interaction validity
weak/spam relationships:
reduced reward impact
10. Clan Integration
10.1 Clan as Relationship Accelerator
clan members can:
discover each other
more easily form friendships
10.2 Not Automatic Friends
being in a clan ≠ friendship
10.3 Clan Roles
Clan Officer / Leader:
may have:
extended discovery tools

⚠️ Future spec required

11. Event System Integration
11.1 Input Events
friend.requested
friend.accepted
friend.removed
11.2 Output Events
friendship.created
friendship.activated
friendship.removed
11.3 Validation Hooks

Before acceptance:

Check:
- age compatibility
- rate limits
- friend caps
12. Observability Integration

Track:

friend graph structure
growth velocity
interaction quality

Used for:

fraud detection
system tuning
13. Constraints
13.1 No Anonymous Relationships
all relationships tied to identity
13.2 No Bulk Actions
cannot:
send mass friend requests
accept in bulk
13.3 No External Linking
friendships only exist within platform
14. Missing / Future Specs
14.1 Exact Rate Limits
requests/hour
friends/day
14.2 Friend Cap Values
max total friends
14.3 Relationship Strength Formula
scoring model
14.4 Clan Permissions
officer vs leader powers