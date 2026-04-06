# AD‑TO‑CASH REWARDS — PLANNING DOCUMENT

## Purpose
Define a safe, deterministic system that allows players to earn a small percentage of real‑world cash from ads, redeemable for gift cards. The system must increase engagement and retention without introducing moderation, fraud risk, or pay‑to‑win dynamics.

## Goals
- Increase ad engagement across EndlessRadio, EndlessTube, EndlessTV, and offerwalls.
- Provide a tangible real‑world reward without compromising platform safety.
- Maintain deterministic, transparent reward rules.
- Integrate cleanly with EndlessCoin, Memberships, and Leveling perks.
- Ensure zero moderation, zero user‑generated content, and zero payout risk.

## Personas
- **Casual Player:** Wants small real‑world rewards for passive engagement.
- **Engaged Grinder:** Optimizes ad surfaces for maximum earnings.
- **Member:** Wants bonuses and control over which ads they see.
- **Creator:** Benefits indirectly from increased platform engagement.

## User Stories
- *As a player, I want to earn a small amount of cash from ads so I feel rewarded for my time.*
- *As a member, I want bonuses on cash earnings so membership feels valuable.*
- *As a player, I want clear rules so I know exactly how much I earn from each ad type.*
- *As the platform, I need deterministic rules to prevent abuse or fraud.*

## Core Capabilities
- Cash balance tracking.
- Reward split calculation (EndlessCoin vs cash).
- Gift card redemption flow.
- Eligibility rules per ad surface.
- Membership bonus integration.
- Leveling perk integration.
- Fraud‑resistant earning logic.

## Reward Split
- **90–95% EndlessCoin**  
- **5–10% Cash**  
- Configurable per ad type.

## Eligible Surfaces
- EndlessRadio impressions  
- EndlessTube long‑form ads  
- EndlessTV blocks  
- Offerwalls  
- Sponsored ads  

## Workflows

### 1. Ad Impression → Reward Calculation
1. Ad completes.  
2. System determines ad type.  
3. Apply reward split.  
4. Add EndlessCoin to wallet.  
5. Add cash to Cash Balance.  
6. Apply membership bonuses.  
7. Apply leveling perks.  
8. Log event for fraud detection.

### 2. Cash‑Out Flow
1. Player reaches $10 minimum.  
2. Player selects gift card brand.  
3. System generates redemption code.  
4. Cash Balance decreases.  
5. Confirmation logged.

## Rules
- No direct cash payouts.  
- No external payment details collected.  
- No user‑generated content.  
- No cash earnings from disabled ad types.  
- Membership bonuses apply only to enabled surfaces.

## Constraints
- Must be fraud‑resistant.  
- Must not incentivize botting.  
- Must not create pay‑to‑win dynamics.  
- Must remain sustainable at scale.

## Success Criteria
- Increased ad engagement.  
- Increased membership conversions.  
- High redemption satisfaction.  
- Zero fraud incidents.  
- Zero moderation required.
