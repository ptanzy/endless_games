# EndlessOS — Motion Guidelines

## Purpose
The EndlessOS motion system defines how movement, transitions, and animations behave across the platform.  
Motion exists to support clarity, reinforce hierarchy, and reduce cognitive load.  
It must never distract, surprise, or compete with content.

This document outlines:
- Motion philosophy  
- Timing and easing  
- Allowed vs. prohibited motion  
- Component‑level behaviors  
- Platform‑level constraints  
- Accessibility considerations  
- Anti‑patterns  

Motion is a system‑level asset and must remain consistent across all platforms.

---

# Core Principles

## 1. Calm, Predictable, Intentional
Motion must feel:
- Subtle  
- Warm  
- Supportive  
- Never abrupt  
- Never decorative  

Motion should help the user understand:
- What changed  
- Where it came from  
- Where it is going  

If motion does not improve clarity, it must not exist.

---

## 2. Zero Surprise
Motion must never:
- Jump  
- Snap  
- Overshoot  
- Bounce  
- Elastic  
- Parallax  
- Warp  
- Rotate  
- Scale aggressively  

EndlessOS motion is grounded, stable, and deterministic.

---

## 3. No Layout Shift
Motion must never cause:
- Reflow  
- Recalculation of layout  
- Content shifting under the user  
- Tooltip flicker  
- Button movement  

Layout must remain stable at all times.

---

## 4. Motion Supports Function, Not Identity
Motion is not branding.  
Motion is not decoration.  
Motion is not personality.

Motion exists to:
- Reinforce hierarchy  
- Guide attention  
- Confirm interaction  
- Reduce cognitive load  

Identity is expressed through color, layout, and platform surfaces — not motion.

---

# Timing & Easing

EndlessOS uses a **three‑tier timing scale**:

| Speed | Duration | Usage |
|--------|-----------|--------|
| Fast | 120ms | Small UI changes, hover states |
| Medium | 180ms | Component transitions |
| Slow | 240ms | Page‑level transitions |

### Easing Functions
- **Ease‑out** → Entrances  
- **Ease‑in** → Exits  
- **Ease‑in‑out** → State changes  

### Rules:
- No custom timing values  
- No spring physics  
- No bounce curves  
- No elastic curves  
- No cubic‑bezier experimentation  

Motion must remain predictable and consistent.

---

# Allowed Motion

## 1. Opacity Fades (Subtle Only)
- 0 → 1 for entrances  
- 1 → 0 for exits  
- Must be smooth, no flicker  
- Must not be used for tooltips that require copying text  

## 2. Position Shifts (Small, Linear)
- 2–4px max  
- Only for clarity (e.g., dropdown opening)  
- Must not cause layout shift  

## 3. Scale (Micro Only)
- 98% → 100%  
- Only for buttons on press  
- Must be subtle and fast  

## 4. Progress Indicators
- Loading wheel rotation  
- Determinate progress bar fill  
- Indeterminate shimmer (very subtle)  

## 5. Page Transitions
- Fade in/out  
- Slide 4–8px max  
- No parallax  
- No multi‑layer motion  

---

# Prohibited Motion

The following are strictly forbidden:

### ❌ Bounce  
### ❌ Elastic  
### ❌ Parallax  
### ❌ Overshoot  
### ❌ Spring physics  
### ❌ Large‑scale movement  
### ❌ Rotation (except loading wheel)  
### ❌ 3D transforms  
### ❌ Perspective motion  
### ❌ Zooming UI  
### ❌ Morphing icons  
### ❌ Color‑shifting animations  
### ❌ Tooltip fade‑in/out that causes flicker  
### ❌ Motion that recomputes layout  

These violate the calm, predictable nature of EndlessOS.

---

# Component‑Level Motion Rules

## Buttons
- Press: 98% → 100% scale (120ms)  
- Hover: subtle opacity shift  
- No sliding, bouncing, or glowing  

## Cards
- Hover: 2px elevation shift (shadow only)  
- No movement  
- No scale  

## Modals
- Fade in (180ms)  
- Fade out (180ms)  
- Optional 4px upward shift  

## Navigation
- No sliding menus  
- No animated tab bars  
- No animated underlines  

## Tooltips
- Appear instantly  
- No fade  
- No motion  
- Must remain stable for copying text  

## Lists
- No animated reordering  
- No animated insertion  
- No animated deletion  

---

# Platform‑Level Motion

Platforms may not override:
- Timing  
- Easing  
- Motion types  
- Prohibited motion list  

Platforms may override:
- Page‑level transitions (within limits)  
- Loading animations (within limits)  

Platform overrides must:
- Remain subtle  
- Remain predictable  
- Never introduce new motion types  

---

# Accessibility

EndlessOS supports a **Reduced Motion Mode**.

### When enabled:
- All motion durations are cut by 50%  
- All non‑essential motion is removed  
- Page transitions become instant  
- Loading animations become static  

Reduced motion must not break layout or clarity.

---

# Anti‑Patterns

The following are not allowed:
- Motion that draws attention to itself  
- Motion that expresses personality  
- Motion that uses accent colors  
- Motion that changes based on content  
- Motion that causes layout shift  
- Motion that introduces unpredictability  
- Motion that creates visual noise  

These violate the EndlessOS motion philosophy.

---

# Future Expansion

Future documents will define:
- Component‑specific motion specs  
- Platform‑specific transition variants  
- Motion tokens (timing, easing, distance)  
- Motion accessibility testing  
- Motion for controller vs. mouse vs. touch  

---

# Summary

The EndlessOS motion system is calm, predictable, and cinematic.  
It uses subtle fades, micro‑movement, and strict timing rules to support clarity without distraction.  
Motion is functional, not expressive — ensuring a stable, trustworthy experience across the entire platform.
