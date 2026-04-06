REWARD FORMULA (PRODUCTION SPEC)
docs/Planning_V3/03_economy/REWARD_FORMULA.md
Core Model
Reward Value =
  Base Event Value
  × Engagement Weight
  × Quality Multiplier
  × Diversity Multiplier
  × Risk Modifier
Components
1. Base Event Value

Defined per event type:

game.session.completed = 1.0
content.view = 0.2
interaction.valid = 0.5
2. Engagement Weight
min(session_duration / expected_duration, 1.0)

Prevents:

quick farming
shallow sessions
3. Quality Multiplier
based on:
- performance
- completion success
- interaction depth

Range: 0.5 → 1.5
4. Diversity Multiplier
unique_players / total_players

Range: 0.3 → 1.0

Penalizes:

repeated same-group farming
5. Risk Modifier
Risk Score 0–100 →

0–20 → 1.0
21–50 → 0.7
51–80 → 0.3
81–100 → 0.0
Output Distribution

After reward value:

85% → EndlessCoin
10% → EndlessGold
5% → EndlessReward
Creator Split
Creator Share = 25% of total generated value