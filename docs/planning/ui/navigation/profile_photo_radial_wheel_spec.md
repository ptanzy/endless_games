# EndlessOS — Profile Photo Radial Wheel Specification

## Purpose
The Profile Photo Radial Wheel is the **primary global navigation anchor** of EndlessOS.  
It provides fast access to:

- Back  
- Hub  
- Utility pages  
- System actions  
- (Future) Platform Switcher  
- Account actions  

The wheel must remain:
- Deterministic  
- Console‑grade  
- Cinematic  
- Symmetrical  
- Future‑proof  
- Non‑adaptive  

This document defines the geometry, behavior, motion, and interaction model of the radial wheel.

---

# Core Philosophy

## 1. The Wheel Is a Global Navigation Surface
The wheel is not:
- A menu  
- A modal  
- A utility panel  
- A platform‑local control  

It is a **global navigation surface** that sits above all pages.

---

## 2. The Wheel Must Be Deterministic
The wheel must:
- Always open the same way  
- Always place icons in the same positions  
- Never adapt based on context  
- Never reorder icons  
- Never collapse icons  

Predictability is mandatory.

---

## 3. The Wheel Must Be Symmetrical
The wheel must:
- Maintain perfect radial symmetry  
- Maintain even spacing  
- Maintain consistent radius  
- Maintain consistent icon sizing  

Even when icons are invisible (e.g., reserved slot), geometry must remain stable.

---

# Wheel Structure

The wheel consists of:

[Utility]
[Utility]   [Utility]

[Back]   [Reserved Slot]   [Hub]

[Utility]   [Utility]
[Utility]

Code

### Bottom Row (Navigation Row)
- Left: **Back**  
- Center: **Reserved Slot (Platform Switcher)**  
- Right: **Hub**  

### Upper Arc (Utility Row)
- 3–5 utility icons depending on configuration  
- Evenly spaced  
- Neutral icons only  

### Center
- Profile photo  
- Wheel expands outward from this anchor  

---

# Reserved Slot (Platform Switcher)

The bottom‑center slot is reserved for the future Platform Switcher.

In v1:
- Invisible  
- Non‑interactive  
- Not in accessibility tree  
- Not rendered  
- Not focusable  

But the geometry includes it.

See: `reserved_space_for_platform_switcher_spec.md`

---

# Geometry

## Radius
- 96–128px from profile photo center  
- Must remain constant across all pages  

## Icon Size
- 32–40px  
- Must remain constant  

## Spacing
- Even angular spacing  
- 7 total nodes (including reserved slot)  

## Angular Layout
- Back: 225°  
- Reserved Slot: 270°  
- Hub: 315°  
- Utility icons: 0° → 180° arc  

---

# Interaction Model

## Opening the Wheel
The wheel opens when:
- The user clicks the profile photo  
- The user taps the profile photo  
- The user triggers a controller shortcut (future)  

Opening the wheel:
- Resets auto‑hide timer  
- Does not affect the navigation stack  

## Closing the Wheel
The wheel closes when:
- The user clicks outside the wheel  
- The user taps outside the wheel  
- The user presses Back  
- The user selects an icon  
- The user scrolls (optional)  

Closing the wheel:
- Does not affect the navigation stack  
- Does not trigger navigation unless an icon was selected  

---

# Icon Behavior

## Back
- Pops one entry from the navigation stack  
- If a modal is open → closes modal  
- If a wheel is open → closes wheel first  

## Hub
- Clears the navigation stack  
- Returns to Hub  

## Utility Icons
- Push utility pages onto the stack  
- Never replace entries  
- Never collapse entries  

## Reserved Slot (v1)
- No hover  
- No focus  
- No click  
- No tooltip  

---

# Motion Rules

## Opening Animation
- 120–150ms fade  
- 2–4px micro‑shift outward  
- No scale  
- No bounce  
- No rotation  
- No parallax  

## Closing Animation
- 120–150ms fade  
- No collapse animation  
- No inward motion  

The wheel must feel calm and console‑grade.

---

# Safe Zone Compliance

The wheel must:
- Always remain inside safe zones  
- Never clip screen edges  
- Never resize to fit  
- Never reposition dynamically  

If the profile photo is near an edge:
- The wheel shifts slightly inward  
- But spacing and geometry remain identical  

---

# Accessibility

## Focus Order
- Back  
- Reserved Slot (skipped in v1)  
- Hub  
- Utility icons (clockwise)  

## Screen Reader
- Announces: “Navigation wheel opened”  
- Announces each icon by name  
- Announces: “Navigation wheel closed”  

## Controller Navigation (future)
- Radial directional navigation  
- Snap to nearest icon  

---

# Anti‑Patterns

The wheel must never:
- Reorder icons  
- Adapt based on context  
- Use platform identity  
- Use accent colors  
- Animate aggressively  
- Shift layout  
- Replace the top layer  
- Trigger platform switching in v1  
- Display the reserved slot visually in v1  

These violate the EndlessOS navigation doctrine.

---

# Summary

The Profile Photo Radial Wheel is the global navigation anchor of EndlessOS.

It must remain:
- Deterministic  
- Symmetrical  
- Console‑grade  
- Future‑proof  
- Identity‑neutral  

The wheel provides:
- Back  
- Hub  
- Utility access  
- Future platform switching  

And it does so without ever altering the navigation stack or shifting layout.