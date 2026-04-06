# EndlessOS — Utility Navigation Specification

## Purpose
The Utility Navigation System provides quick access to system‑level and account‑level utilities while keeping the top navigation bar minimal, clean, and cinematic.  
It uses a combination of **single‑utility icons** and **multi‑utility radial wheels** to compress complexity without visual clutter.

This specification defines:
- Utility bar structure  
- Icon behavior  
- Radial wheel behavior  
- Hover, focus, and touch interactions  
- Safe zone compliance  
- Motion rules  
- Icon grouping logic  
- Placement within the EndlessOS documentation structure  

It inherits from:
- layout_design_doctrine.md  
- layout_system_overview.md  
- safe_zone_rules.md  
- tooltip_spec.md  
- visual_language_design.md  

---

# Core Principles

## 1. Minimal Top Bar
The utility navigation bar must remain:
- minimal  
- uncluttered  
- identity‑neutral  
- visually calm  

The bar should contain **as few icons as possible**, using grouping and radial wheels to compress complexity.

---

## 2. Deterministic Behavior
Utility navigation must:
- behave the same way every time  
- never shift layout  
- never resize dynamically  
- never adapt based on content  
- never animate aggressively  

Determinism is mandatory.

---

## 3. Neutral Visual Language
Utility icons and wheels must:
- use neutral colors  
- use neutral backgrounds  
- use neutral borders  
- use neutral iconography  
- avoid accent colors  
- avoid semantic colors  

Utility navigation must never express platform identity.

---

## 4. Hover Is Allowed but Non‑Essential
Hover may trigger:
- radial wheel expansion  
- tooltips  

Hover must never:
- reveal required information  
- be the only way to access utilities  
- shift layout  

Touch and keyboard must have full access.

---

# Utility Navigation Structure

The utility navigation bar sits at the **top‑right** of every page, inside the safe zone.

Structure:
┌──────────────────────────────────────────────┐
│ [Platform Header]                            │
│                                [Utility Bar] │
└──────────────────────────────────────────────┘

Code

The utility bar contains:
- Single‑utility icons  
- Multi‑utility icons (wheel triggers)  
- Profile photo wheel (global utilities)  

---

# Icon Types

## 1. Single‑Utility Icons
These represent a single destination:
- Settings  
- Legal  
- Help  
- Feedback  
- Storage  
- Updates  

Behavior:
- Hover → optional tooltip  
- Click → navigate  
- No wheel  

Size:
- 28–32px icon  
- 24px padding around hitbox  

---

## 2. Multi‑Utility Icons (Wheel Triggers)
These represent a **category** of utilities:
- System (Settings, Storage, Updates)  
- Support (Help, Contact, FAQ)  
- Account (Membership, Wallet, Rewards)  
- Legal (Terms, Privacy, Licenses)  

Behavior:
- Hover → expand radial wheel  
- Focus → expand radial wheel  
- Touch → open neutral popover version  

Size:
- 32px parent icon  
- 20–24px child icons  

---

# Radial Wheel Specification

## 1. Expansion Behavior
Trigger:
- Hover (desktop)  
- Focus (keyboard)  
- Tap (touch → popover fallback)  

Animation:
- 120–150ms opacity fade  
- No scale  
- No bounce  
- No rotation  
- No parallax  

The wheel must feel calm and cinematic.

---

## 2. Wheel Layout
The wheel contains **2–6 child icons**, evenly spaced around the parent.

Rules:
- Expand inward (toward screen center)  
- Never break safe zones  
- Never clip edges  
- Never overlap critical UI  
- Never shift layout  

Spacing:
- 8–12px between icons  
- 24px minimum radius  
- 32–40px maximum radius  

---

## 3. Child Icons
Child icons represent individual utilities.

Rules:
- Neutral color only  
- Neutral background  
- 1px neutral border  
- 20–24px icon size  
- 8px padding  

Hover:
- Subtle opacity emphasis  
- Optional tooltip  

Click:
- Navigate to utility page  

---

# Interaction Model

## Hover
Hover may:
- Expand wheel  
- Show tooltip  

Hover must not:
- Reveal required information  
- Shift layout  
- Animate aggressively  

## Focus
Focus must:
- Expand wheel  
- Follow predictable order  
- Never trap the user  

## Touch
Touch behavior:
- Tap parent icon → open neutral popover  
- Tap child icon → navigate  
- Tap outside → close  

Popover must:
- Respect safe zones  
- Use neutral styling  
- Never animate aggressively  

---

# Safe Zone Compliance

Utility navigation must:
- Sit fully inside safe zones  
- Expand wheels inward  
- Never collide with edges  
- Never clip tooltips  
- Never exceed safe zone boundaries  

If a wheel would violate safe zones:
- Reduce radius  
- Reposition slightly inward  
- Never overflow  

---

# Motion Rules

Allowed:
- Opacity fade (120–150ms)  
- Micro‑shift (≤2px)  

Prohibited:
- Bounce  
- Elastic  
- Parallax  
- Rotation  
- Scaling  
- Morphing  

Motion must support clarity, not personality.

---

# Icon Grouping Logic

Utilities must be grouped logically:

### System
- Settings  
- Storage  
- Updates  
- Device Info  

### Support
- Help  
- Contact  
- FAQ  
- Troubleshooting  

### Account
- Membership  
- Wallet  
- Rewards  
- Subscriptions  

### Legal
- Terms  
- Privacy  
- Licenses  

Grouping must:
- Reduce top bar clutter  
- Keep icon count minimal  
- Scale as utilities grow  

---

# Anti‑Patterns

The following violate the utility navigation doctrine:

- Too many icons in the top bar  
- Accent‑colored utility icons  
- Wheels that shift layout  
- Wheels that animate aggressively  
- Hover‑dependent required information  
- Wheels that break safe zones  
- Dropdowns replacing wheels  
- Text‑heavy menus  
- Dynamic resizing  
- Platform‑specific utility layouts  

These are strictly prohibited.

---

# Summary

The EndlessOS Utility Navigation System keeps the top bar minimal while providing fast access to system and account utilities.  
It uses a deterministic, cinematic radial wheel pattern that is already established through the profile photo interaction.

This system:
- Compresses complexity  
- Prevents clutter  
- Scales cleanly  
- Respects safe zones  
- Matches the EndlessOS visual language  
- Maintains a calm, console‑grade aesthetic  