RULE TEMPLATE LIBRARY (V3)
1. Purpose

The Rule Template Library defines:

the allowed building blocks for games
how creators construct gameplay
constraints that prevent exploitative mechanics

This system ensures:

All games are expressive but structurally safe and economically valid

2. Core Principles
2.1 Composition Over Code
games are built by:
combining templates
NOT writing arbitrary logic
2.2 Finite Action Space
all player actions must come from:
predefined sets
2.3 Bounded Outcomes
no infinite loops
no unbounded scoring
2.4 Verifiable State
all game states must be:
deterministic
reconstructable
3. Template Structure

Each rule template contains:

Template ID
Category
Inputs
Outputs
Constraints
Validation Rules
4. Core Template Categories
🎮 4.1 ACTION TEMPLATES

Define what players can do.

Example: Basic Action
Template: ACTION_SIMPLE_INPUT

Inputs:
- player input (tap, click, move)

Outputs:
- action event

Constraints:
- rate-limited
- time-bound
Example: Timed Action
Template: ACTION_TIMED_RESPONSE

Inputs:
- stimulus event

Outputs:
- success/failure

Constraints:
- reaction window (e.g. 200–1500ms)
🧩 4.2 OBJECTIVE TEMPLATES

Define goals.

Example: Score Target
Template: OBJECTIVE_SCORE_THRESHOLD

Goal:
- reach X score within time

Constraints:
- max score cap
- time limit required
Example: Survival
Template: OBJECTIVE_SURVIVAL

Goal:
- survive for duration

Constraints:
- max duration cap
🏁 4.3 SESSION TEMPLATES

Define session structure.

Example: Fixed Duration
Template: SESSION_FIXED_TIME

Parameters:
- duration (30s–10min)

Constraint:
- must end automatically
Example: Round-Based
Template: SESSION_ROUNDS

Parameters:
- number of rounds
- round duration

Constraint:
- total session cap enforced
⚖️ 4.4 SCORING TEMPLATES

Define how performance is measured.

Example: Incremental Score
Template: SCORE_INCREMENTAL

Inputs:
- actions

Outputs:
- score += value

Constraints:
- max increments per second
- diminishing returns
Example: Accuracy Score
Template: SCORE_ACCURACY

Outputs:
- % correct actions

Constraints:
- minimum action count required
🤝 4.5 MULTIPLAYER TEMPLATES
Example: Competitive Match
Template: MULTI_COMPETITIVE

Players:
- 2–N

Output:
- ranked result

Constraints:
- must include performance differentiation
Example: Cooperative Task
Template: MULTI_COOP

Players:
- 2–N

Goal:
- shared objective

Constraints:
- individual contribution tracked
🔁 4.6 PROGRESSION TEMPLATES
Example: Level Progression
Template: PROGRESSION_LEVEL

Parameters:
- levels
- difficulty scaling

Constraints:
- max level cap
🚫 5. ANTI-EXPLOIT RULES (GLOBAL)
5.1 Loop Prevention
No template may:
- allow infinite repeat without variation
5.2 Minimum Effort Requirement
All sessions must:
- require measurable interaction
5.3 Time Normalization
Reward signals must scale with time
5.4 Diversity Requirement
Repeated identical actions:
- lose scoring value
🔗 6. TEMPLATE COMPOSITION RULES
6.1 Required Components

Every game must include:

1 Action Template
1 Objective Template
1 Session Template
1 Scoring Template
6.2 Optional Components
Multiplayer Template
Progression Template
6.3 Forbidden Combinations
no:
infinite scoring + infinite time
zero-skill outcomes
passive reward generation
🧪 7. VALIDATION RULES

Before approval, system checks:

7.1 Complexity Check
must exceed:
minimum interaction threshold
7.2 Loop Detection
repeated state cycles → rejected
7.3 Reward Signal Validity
must produce:
meaningful signals
7.4 Difficulty Validation
must:
require effort
not be trivial
📊 8. DIFFICULTY MODEL (INITIAL)
Difficulty Score
Difficulty =
  Reaction Complexity
+ Decision Complexity
+ Time Pressure
Constraints
Min Difficulty Threshold required for approval
🔌 9. SDK INTEGRATION

Creators interact via:

Select Templates →
Configure Parameters →
Preview Game →
Submit
🔍 10. OBSERVABILITY INTEGRATION

Track:

template usage patterns
exploit-prone combinations
performance distribution
🟡 11. OPEN DECISIONS
Template Expansion Strategy
how often new templates added
Difficulty Threshold Values
exact scoring thresholds
Template Limits
max templates per game