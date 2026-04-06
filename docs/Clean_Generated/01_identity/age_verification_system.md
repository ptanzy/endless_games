RISK SCORE SYSTEM (PRODUCTION SPEC)
docs/Planning_V3/09_data_observability/RISK_SCORE_SYSTEM.md
Score Range
0 → 100
Components
Risk Score =
  Activity Anomaly Score (30%)
+ Social Graph Risk (20%)
+ Reward Pattern Risk (25%)
+ Device / Session Risk (15%)
+ History Penalty (10%)
Key Signals
Activity Anomaly
extreme session counts
perfect timing
Social Graph Risk
dense clusters
repeated same users
Reward Pattern Risk
identical reward loops
abnormal velocity
Device Risk
multiple accounts per device
rapid switching
Decay System
Risk decays over time if behavior normalizes
Enforcement Mapping
Score	Action
0–20	none
21–50	reward reduction
51–80	earning restrictions
81–100	full block