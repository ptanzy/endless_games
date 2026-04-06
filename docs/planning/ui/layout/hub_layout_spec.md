# EndlessOS — Hub Layout Specification

## Purpose
The Hub is the **central world selector** of EndlessOS.  
It is a full‑screen, cinematic surface used exclusively for switching between platforms:

- EndlessGames  
- EndlessMusic  
- EndlessTube  
- EndlessStream  
- EndlessRadio  
- EndlessBooks  
- EndlessEvents  
- EndlessMoments  
- EndlessRecaps  

The Hub must remain:
- Calm  
- Spacious  
- Identity‑neutral  
- Deterministic  
- Free of utility clutter  
- Free of platform identity  

This document defines the **structural layout** of the Hub.

---

# Core Layout Philosophy

## 1. The Hub Is a Cinematic Surface
The Hub is the most visually expressive surface in EndlessOS, but it must remain:
- Minimal  
- Spacious  
- Calm  
- Non‑interactive outside of platform tiles  

It is not a dashboard.  
It is not a utility surface.  
It is not a navigation bar.

---

## 2. The Hub Must Be Identity‑Neutral
The Hub must never use:
- Platform accent colors  
- Platform backgrounds  
- Platform typography  

It must use:
- Neutral background  
- Neutral typography  
- Neutral iconography  

Platform identity appears **only after** selecting a platform.

---

## 3. The Hub Must Be Deterministic
The Hub must:
- Always load the same way  
- Always show the same platform order  
- Never reorder tiles dynamically  
- Never adapt based on usage  
- Never personalize layout  

Consistency is mandatory.

---

# Hub Structure

The Hub layout is composed of:

┌──────────────────────────────────────────────┐
│ Top Layer (Auto‑Hide)                        │
│   - Profile Photo + Wheel                    │
│   - Utility Navigation Bar                   │
│   - Utility Mini‑Carousel                    │
├──────────────────────────────────────────────┤
│ Safe Zone                                     │
│  ┌────────────────────────────────────────┐   │
│  │ Hub Title (Optional)                   │   │
│  ├────────────────────────────────────────┤   │
│  │ Platform Tile Grid                     │   │
│  ├────────────────────────────────────────┤   │
│  │ Optional Footer Notes                  │   │
│  └────────────────────────────────────────┘   │
└──────────────────────────────────────────────┘

Code

---

# 1. Top Layer (Auto‑Hide)

The Hub uses the same top layer as all other pages:
- Profile photo + radial wheel  
- Utility navigation bar  
- Utility mini‑carousel  

The top layer:
- Appears on load  
- Auto‑hides after 10–20 seconds  
- Reappears when the user moves the mouse to the top  

The Hub itself never hides — only the top layer does.

---

# 2. Hub Title (Optional)

The Hub may optionally include a title such as:
- “EndlessOS”  
- “Choose Your World”  
- “Select a Platform”  

Rules:
- Neutral typography  
- 32–40px weight 600  
- Centered  
- 48px top padding  
- 24px bottom padding  
- Must not use accent colors  
- Must not animate  

The title is optional and may be omitted for a cleaner cinematic look.

---

# 3. Platform Tile Grid

The platform tile grid is the core of the Hub.

## Grid Rules
- 3‑column grid on large screens  
- 2‑column grid on medium screens  
- 1‑column grid on small screens  
- 48px vertical spacing  
- 32px horizontal spacing  
- Centered within safe zones  

## Tile Size
Tiles must be:
- Large  
- Cinematic  
- Identity‑neutral  
- Consistent across platforms  

Recommended size:
- 280–360px width  
- 180–240px height  

Tiles must never:
- Resize dynamically  
- Change shape  
- Change aspect ratio  
- Animate aggressively  

## Tile Content
Each tile contains:
- Platform icon  
- Platform name  
- Optional short tagline  

All content must be neutral.

## Tile Hover Behavior
Hover may:
- Increase opacity  
- Add subtle glow  
- Add subtle shadow  

Hover must not:
- Shift layout  
- Scale the tile  
- Animate aggressively  
- Reveal required information  

## Tile Click Behavior
Clicking a tile:
- Pushes the platform root page onto the stack  
- Transitions to the platform page  
- Does not open modals  
- Does not open utility pages  

---

# 4. Optional Footer Notes

The Hub may include optional footer content such as:
- Version number  
- Legal text  
- Build identifier  

Rules:
- Neutral typography  
- 12–14px  
- Centered  
- 48px bottom padding  
- Must not distract from platform tiles  

---

# Safe Zone Compliance

The Hub must:
- Respect global safe zones  
- Keep tiles fully inside safe zones  
- Keep the title inside safe zones  
- Keep footer notes inside safe zones  

Tiles must never:
- Touch screen edges  
- Overflow  
- Clip  

---

# Motion Rules

The Hub must use:
- Subtle fade‑in on load (120–150ms)  
- No parallax  
- No bounce  
- No slide  
- No scale  
- No rotation  

The Hub must feel calm and cinematic.

---

# Scroll Behavior

The Hub uses:
- Vertical scroll only  
- No horizontal scroll  
- No snapping  
- No parallax  

Scrolling must be:
- Smooth  
- Neutral  
- Non‑animated  

---

# Anti‑Patterns

The Hub must never include:
- Utility pages  
- Account info  
- Settings  
- Notifications  
- Platform identity  
- Accent colors  
- Dynamic tile ordering  
- Hover‑dependent required info  
- Aggressive animation  
- Horizontal scroll  
- Layout shift  
- Platform‑specific layout hacks  

These violate the EndlessOS layout doctrine.

---

# Summary

The Hub is the **world selector** of EndlessOS.  
It must remain:
- Calm  
- Cinematic  
- Deterministic  
- Identity‑neutral  
- Free of clutter  

The Hub’s layout is simple, spacious, and predictable, ensuring a premium, console‑grade experience.