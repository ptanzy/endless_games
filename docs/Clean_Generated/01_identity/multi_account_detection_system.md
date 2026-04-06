OPEN DECISIONS & GAPS (UPDATED)
1. Purpose

This document tracks:

unresolved system gaps
intentionally flexible decisions
tunable parameters

It ensures:

All non-finalized aspects of the system remain visible, controlled, and revisitable

🔴 2. HARD GAPS (REMAINING)
2.1 Identity
🔴 Multi-Account Detection System
Domain: Identity
System: Identity & Account
Type: HARD GAP
Priority: HIGH
Impact: Prevents reward abuse and fraud
Dependencies: Risk Score System
Status: Unresolved
Source:
docs/Planning_V3/01_identity/IDENTITY_AND_ACCOUNT_SYSTEM.md
🔴 Account Recovery System
Domain: Identity
System: Identity & Account
Type: HARD GAP
Priority: MEDIUM
Impact: Required for user retention
Dependencies: Authentication
Status: Unresolved
🔴 Account Suspension / Ban Logic
Domain: Governance
System: Enforcement
Type: HARD GAP
Priority: HIGH
Impact: Defines final enforcement actions
Dependencies: Risk Score System
Status: Unresolved
2.2 Social
🔴 Friend Caps
Domain: Social
System: Friendship
Type: HARD GAP
Priority: MEDIUM
Impact: Prevents network abuse
Dependencies: Anti-Fraud
Status: Unresolved
🔴 Clan Size Limits
Domain: Social
System: Clan
Type: HARD GAP
Priority: MEDIUM
Impact: Prevents large-scale coordination abuse
Dependencies: Anti-Fraud
Status: Unresolved
2.3 Games
🔴 Rule Template Library
Domain: Games
System: SDK
Type: HARD GAP
Priority: HIGH
Impact: Defines what games can exist
Dependencies: Reward System
Status: Unresolved
2.4 Observability
🔴 Detection Threshold Definitions
Domain: Observability
System: Anti-Fraud
Type: HARD GAP
Priority: HIGH
Impact: Required for enforcement accuracy
Dependencies: Risk Score System
Status: Unresolved
🟡 3. OPEN DECISIONS (UPDATED WITH TIER 1)
3.1 Economy
🟡 Revenue Allocation Ratio
Domain: Economy
System: Reward System
Type: OPEN DECISION
Priority: HIGH
Current Value: 85% Coin / 10% Gold / 5% Reward
Range: Adjustable
Impact: Platform profitability vs user incentives
Dependencies: Ad Revenue Model
Status: ACTIVE
Source:
docs/Planning_V3/03_economy/REWARD_FORMULA.md
🟡 Creator Revenue Share
Domain: Economy
System: Creator Monetization
Type: OPEN DECISION
Priority: HIGH
Current Value: 25%
Range: 20–35%
Impact: Creator growth vs platform margin
Dependencies: Engagement Metrics
Status: ACTIVE
Source:
docs/Planning_V3/03_economy/CREATOR_MONETIZATION_SYSTEM.md
🟡 Reward Weighting Values
Domain: Economy
System: Reward Formula
Type: OPEN DECISION
Priority: HIGH
Items:
- Base Event Values
- Engagement Scaling
- Quality Multiplier Range
- Diversity Multiplier Range
Impact: Core economy balance
Status: ACTIVE
Source:
docs/Planning_V3/03_economy/REWARD_FORMULA.md
🟡 Cash-Out Threshold
Domain: Economy
System: Cash-Out
Type: OPEN DECISION
Priority: MEDIUM
Current Value: $5 minimum
Range: $5–$20
Impact: Fraud risk vs user satisfaction
Status: ACTIVE
Source:
docs/Planning_V3/03_economy/CASH_OUT_SYSTEM.md
3.2 Identity
🟡 Age Verification Method (Refined but Not Final)
Domain: Identity
System: Age Verification
Type: OPEN DECISION
Priority: HIGH
Current Model:
- Self-declared + heuristic validation
Future Options:
- Document verification
- Third-party verification
Impact: Child safety vs onboarding friction
Status: ACTIVE
Source:
docs/Planning_V3/01_identity/AGE_VERIFICATION_SYSTEM.md
3.3 Observability
🟡 Risk Score Weighting
Domain: Observability
System: Risk Score
Type: OPEN DECISION
Priority: HIGH
Current Weights:
- Activity: 30%
- Social: 20%
- Reward: 25%
- Device: 15%
- History: 10%
Impact: Detection sensitivity
Status: ACTIVE
Source:
docs/Planning_V3/09_data_observability/RISK_SCORE_SYSTEM.md
🟡 Enforcement Threshold Mapping
Domain: Observability
System: Enforcement
Type: OPEN DECISION
Priority: HIGH
Current Mapping:
0–20: none
21–50: reduced rewards
51–80: restricted
81–100: blocked
Impact: False positives vs fraud prevention
Status: ACTIVE
3.4 Governance
🟡 Dynamic Permission Overrides
Domain: Governance
System: Permission System
Type: OPEN DECISION
Priority: HIGH
Description:
How aggressively permissions are removed based on risk
Impact: UX vs safety
Status: ACTIVE
✅ 4. RESOLVED (TIER 1 COMPLETE)

These items are no longer gaps:

✔ Reward Formula → Defined
✔ Risk Score System → Defined
✔ Age Verification → Defined (initial model)
✔ Permission Matrix → Defined
✔ Cash-Out System → Defined
🔁 5. SYSTEM RULE
All future uncertainty MUST go here
If it is:
- undefined → HARD GAP
- tunable → OPEN DECISION