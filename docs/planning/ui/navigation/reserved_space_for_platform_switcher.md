# EndlessOS — Reserved Space for Platform Switcher Specification

## Purpose
This specification defines how EndlessOS reserves a **future slot** for a Platform Switcher inside the **profile photo radial wheel**, without implementing the feature in v1.

The goal is to:
- Preserve wheel geometry  
- Preserve spacing  
- Preserve symmetry  
- Avoid redesign in future versions  
- Support future global platform switching  
- Maintain console‑grade navigation consistency  

This is a **structural reservation**, not a functional feature.

---

# Core Principles

## 1. The Platform Switcher Is Not Implemented in v1
In v1:
- The switcher does not appear  
- The switcher is not interactive  
- The switcher is not discoverable  
- The switcher is not in the accessibility tree  

But the **slot for it exists** in the wheel’s geometry.

---

## 2. The Wheel Layout Must Not Change in Future Versions
The radial wheel must be designed **from day one** to include the switcher slot.

This ensures:
- No spacing changes  
- No radius changes  
- No animation changes  
- No safe‑zone changes  
- No rebalancing of icons  

When the switcher is added in v2+, it simply becomes visible.

---

## 3. The Reserved Slot Preserves Symmetry
The radial wheel must feel:
- Balanced  
- Centered  
- Intentional  

Even though the slot is invisible in v1, the wheel’s geometry must treat it as a real node.

---

# Wheel Geometry

The profile photo radial wheel uses a **polar layout** with evenly spaced nodes.

The bottom row is reserved for navigation actions:

[Back]   [Platform Switcher]   [Hub]

### v1 (Current)
- Back  
- **Invisible reserved slot**  
- Hub  

### v2+ (Future)
- Back  
- Platform Switcher  
- Hub  

The geometry is identical in both versions.

---

# Reserved Slot Specifications

## Position
- Angle: **270°** (straight down)  
- Radius: identical to Back and Hub  
- Alignment: bottom‑center  

## Hitbox
- Exists in geometry  
- **Inactive** in v1  
- No hover  
- No focus  
- No click  

## Visual
- No icon  
- No placeholder  
- No opacity  
- No outline  

## Accessibility
- Not focusable  
- Not announced  
- Not navigable  

The slot is **structurally real but visually absent**.

---

# Behavior in v1

In v1, the reserved slot:
- Does not render  
- Does not animate  
- Does not appear in DOM (if web‑based)  
- Does not appear in controller navigation  
- Does not appear in keyboard focus order  

But the wheel:
- Calculates spacing as if the slot exists  
- Maintains perfect symmetry  
- Maintains deterministic geometry  

This prevents future redesign.

---

# Behavior in v2+

When the Platform Switcher is implemented:
- The slot becomes visible  
- The icon appears  
- The hitbox activates  
- The tooltip activates  
- The action becomes available  

No other wheel elements move or resize.

---

# Motion Rules

In v1:
- The slot does not animate  
- It does not fade  
- It does not micro‑shift  

In v2+:
- It inherits standard wheel animation  
  - 120–150ms fade  
  - 2–4px micro‑shift  

---

# Safe Zone Compliance

The reserved slot must:
- Sit fully inside safe zones  
- Never clip  
- Never require wheel resizing  
- Never require wheel repositioning  

The wheel must be designed with the slot included from the start.

---

# Anti‑Patterns

The reserved slot must never:
- Be visible in v1  
- Shift other icons  
- Change wheel radius  
- Change wheel spacing  
- Be repurposed for another feature  
- Be removed  
- Be used as a placeholder  
- Be shown as “coming soon”  

These violate the EndlessOS navigation doctrine.

---

# Summary

The reserved Platform Switcher slot ensures EndlessOS can evolve from:
- **Hub‑only platform switching** (v1)  
to  
- **Global platform switching** (v2+)  

without redesigning the radial wheel.

The slot:
- Is invisible in v1  
- Is fully integrated into wheel geometry  
- Preserves symmetry  
- Future‑proofs navigation  
- Supports hybrid console/web‑app identity  

This is a structural reservation, not a functional feature.