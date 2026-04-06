DETECTION THRESHOLDS (V3)
1. Purpose

Defines:

exact trigger points for fraud detection
thresholds for risk scoring inputs
enforcement activation boundaries

Ensures:

Detection is consistent, measurable, and tunable

2. Threshold Design Principles
2.1 Multi-Signal Requirement
no enforcement triggered by a single signal
minimum:
≥ 2 signals required for action
2.2 Progressive Sensitivity
thresholds tighten as risk increases
2.3 Time-Window Based
all thresholds evaluated over:
Short Window (minutes–hours)
Medium Window (day)
Long Window (week)
2.4 Environment Configurable
all values are:
NOT hardcoded
adjustable
🔍 3. CORE THRESHOLD DEFINITIONS
3.1 Activity Thresholds
High Activity Rate
> 30 sessions/hour → FLAG (Low)
> 60 sessions/hour → FLAG (Medium)
> 100 sessions/hour → FLAG (High)
Continuous Play
> 6 hours continuous → FLAG
> 10 hours continuous → ESCALATE
3.2 Timing Regularity (Bot Signal)
Action Interval Consistency
< 5% variance across 50+ actions → FLAG (Medium)
< 2% variance across 100+ actions → FLAG (High)
3.3 Social Graph Thresholds
Friend Creation Rate
> 10/hour → FLAG
> 25/day → ESCALATE
Repeated Interaction Pairing
> 70% interactions with same user (24h) → FLAG
> 85% interactions with same user (48h) → ESCALATE
Dense Cluster Detection
> 80% of interactions within fixed group (5+ users) → FLAG
3.4 Reward Pattern Thresholds
Reward Velocity
> 3x average user rate → FLAG
> 5x average → ESCALATE
Identical Session Repetition
Same outcome repeated 20+ times → FLAG
Same outcome repeated 50+ times → ESCALATE
Low Diversity Score
Diversity Multiplier < 0.4 → FLAG
< 0.2 → ESCALATE
3.5 Multi-Account Detection Thresholds
Device Overlap
2–3 accounts same device → FLAG
4+ accounts → ESCALATE
Session Switching
> 5 account switches/hour → FLAG
> 10 switches/hour → ESCALATE
Link Confidence Thresholds
Score 50+ → apply soft restrictions
Score 70+ → apply medium restrictions
Score 85+ → apply hard restrictions
3.6 Clan-Based Exploitation
Internal Reward Loop
> 80% rewards from same clan → FLAG
> 90% → ESCALATE
Clan Session Repetition
Same group plays 20+ sessions/day → FLAG
50+ sessions/day → ESCALATE
3.7 Cash-Out Risk Thresholds
Rapid Accumulation
Earn threshold amount in < 24h → FLAG
< 6h → ESCALATE
High Risk Score + Cash-Out
Risk Score > 60 → HOLD
Risk Score > 80 → BLOCK
⚖️ 4. SIGNAL COMBINATION LOGIC
4.1 Flag Aggregation
2 Low Flags → Medium Risk
1 Medium + 1 Low → Medium Risk
2 Medium → High Risk
1 High → High Risk
4.2 Risk Score Injection

Each threshold contributes:

Low → +5 risk
Medium → +15 risk
High → +30 risk
🚨 5. ENFORCEMENT TRIGGERS
5.1 Soft Enforcement

Triggered when:

Risk Score ≥ 30

Actions:

reward reduction
rate limiting
5.2 Medium Enforcement
Risk Score ≥ 60

Actions:

earning disabled
interaction limits
5.3 Hard Enforcement
Risk Score ≥ 85

Actions:

account locked
cash-out blocked
🔁 6. DECAY & RECOVERY
6.1 Risk Decay
No flags for 24h → -5 risk
No flags for 72h → -15 risk
6.2 Behavior Recovery
normal play restores:
rewards
permissions
🧪 7. TUNING LAYER (IMPORTANT)

All thresholds must be:

Configurable via system config
Example Config
activity.max_sessions_per_hour = 60
reward.max_velocity_multiplier = 3.0
social.max_friend_requests_per_day = 25