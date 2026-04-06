## Purpose

The Safety & Risk System defines:

- how harmful or exploitative behavior is detected
- how risk is scored and tracked
- how enforcement actions are applied

This system ensures:

> The platform is resistant to fraud, abuse, and unsafe behavior without relying on manual moderation.

---

## Core Principles

### Prevention Over Detection
- Systems must prevent abuse structurally
- Detection is secondary

### Continuous Risk Scoring
- Every user has a dynamic risk score

### Multi-Signal Detection
- No single signal determines risk
- Multiple signals combined

### Progressive Enforcement
- Enforcement scales with severity and confidence

### Non-Bypassable
- Risk system cannot be bypassed by any system

# Additional Detailed Sections

## Detection Systems

### Multi-Account Detection
#### Signals
- Device overlap
- IP patterns
- Session timing overlap
- Behavior similarity
- Interaction graph overlap
#### Link Score
0–49 → low confidence
50–69 → moderate
70–84 → high
85+ → critical
#### Enforcement
- Moderate: monitor
- High: reduce rewards
- Critical: restrict accounts

### Gameplay Exploit Detection
#### Signals
- Repeated identical sessions
- Abnormal scoring patterns
- Low variance gameplay
#### Detection
- Pattern recognition
- Statistical thresholds

### Interaction Abuse Detection
#### Signals
- Repeated interaction with same users
- Tight interaction clusters
- Abnormal friend graphs

### Reward Abuse Detection
#### Signals
- Reward spikes
- Inconsistent effort-to-reward ratio

### Automation Detection
#### Signals
- Perfect timing patterns
- Zero variance behavior
- Superhuman consistency

---

## Rule Engine
### Rule Structure
- rule_id
- signal
- threshold
- action
- severity
### Example
IF repeated_sessions > threshold THEN increase risk_score by X

---

## Enforcement System
### Soft Enforcement
- Reduce rewards
- Limit interactions
### Medium Enforcement
- Restrict features
- Increase validation
### Hard Enforcement
- Block actions
- Suspend account
### Critical Enforcement
- Full ban
- Cashout denial

---

## Dynamic Restrictions
### Risk-Based Limits
- High risk: lower reward caps, restricted gameplay
### System Integration
- Permissions modified dynamically
- Feature access reduced

---

## Feedback Loop
Events → Detection → Risk Score → Enforcement → Behavior Change → Updated Risk

---

## Observability
Track:
- Risk distribution
- Detection accuracy
- False positives
- Enforcement outcomes

---

## Edge Cases
### Legitimate High Skill
- Avoid penalizing skill
### Shared Environments
- Detect but do not over-penalize
### New Users
- Lower thresholds initially

---

## Open Decisions
- Exact thresholds
- False positive tolerance
- Automation detection strictness
# Safety, Risk & Anti-Fraud System

---

## Risk Model

### Risk Score
0–29 → Low Risk
30–59 → Moderate Risk
60–79 → High Risk
80–100 → Critical Risk

### Risk Sources
- Gameplay behavior
- Interaction patterns
- Reward anomalies
- Account linking

---

## Detection Systems

### Multi-Account Detection
#### Signals
- Device overlap
- IP patterns
- Session timing overlap
- Behavior similarity
- Interaction graph overlap
#### Link Score
0–49 → low confidence
50–69 → moderate
70–84 → high
85+ → critical
#### Enforcement
- Moderate: monitor
- High: reduce rewards
- Critical: restrict accounts

### Gameplay Exploit Detection
#### Signals
- Repeated identical sessions
- Abnormal scoring patterns
- Low variance gameplay
#### Detection
- Pattern recognition
- Statistical thresholds

### Interaction Abuse Detection
#### Signals
- Repeated interaction with same users
- Tight interaction clusters
- Abnormal friend graphs

### Reward Abuse Detection
#### Signals
- Reward spikes
- Inconsistent effort-to-reward ratio

### Automation Detection
#### Signals
- Perfect timing patterns
- Zero variance behavior
- Superhuman consistency

---

## Rule Engine
### Rule Structure
- rule_id
- signal
- threshold
- action
- severity
### Example
IF repeated_sessions > threshold THEN increase risk_score by X

---

## Enforcement System
### Soft Enforcement
- Reduce rewards
- Limit interactions
### Medium Enforcement
- Restrict features
- Increase validation
### Hard Enforcement
- Block actions
- Suspend account
### Critical Enforcement
- Full ban
- Cashout denial

---

## Dynamic Restrictions
### Risk-Based Limits
- High risk: lower reward caps, restricted gameplay
### System Integration
- Permissions modified dynamically
- Feature access reduced

---

## Feedback Loop
Events → Detection → Risk Score → Enforcement → Behavior Change → Updated Risk

---

## Observability
Track:
- Risk distribution
- Detection accuracy
- False positives
- Enforcement outcomes

---

## Edge Cases
### Legitimate High Skill
- Avoid penalizing skill
### Shared Environments
- Detect but do not over-penalize
### New Users
- Lower thresholds initially

---

## Open Decisions
- Exact thresholds
- False positive tolerance
- Automation detection strictness