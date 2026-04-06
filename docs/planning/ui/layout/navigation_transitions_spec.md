# EndlessOS — Navigation Transitions Specification

## Purpose
Navigation transitions define how EndlessOS visually moves between:
- Hub  
- Platform pages  
- Utility pages  
- Modals  
- Wheels  
- System overlays  

Transitions must remain:
- Cinematic  
- Calm  
- Deterministic  
- Identity‑neutral  
- Non‑adaptive  
- Free of layout shift  

This document defines the motion rules for all navigation transitions.

---

# Core Philosophy

## 1. Motion Supports Clarity, Not Personality
Transitions must:
- Reinforce spatial understanding  
- Reduce cognitive load  
- Maintain platform identity  
- Never distract  

Motion is functional, not expressive.

---

## 2. Transitions Must Be Deterministic
Every navigation action must:
- Use the same timing  
- Use the same easing  
- Use the same micro‑shift  
- Never adapt based on context  

Predictability is mandatory.

---

## 3. Transitions Must Never Shift Layout
Transitions occur **above** the layout.

They must never:
- Push content  
- Resize content  
- Cause reflow  
- Change scroll position  

---

# Transition Types

### 1. Page Entry Transition  
Used when:
- Navigating into a platform  
- Opening a utility page  
- Opening a platform sub‑page  

### 2. Page Exit Transition  
Used when:
- Navigating back  
- Returning to Hub  
- Closing a utility page  

### 3. Modal Transition  
Used when:
- Opening or closing modals  

### 4. Wheel Transition  
Used when:
- Opening or closing radial wheels  

### 5. System Overlay Transition  
Used when:
- Displaying system‑level alerts  

---

# Motion Rules

## Timing
- **120–150ms** total duration  
- Fixed per OS version  

## Easing
- Standard cubic ease:  
  `cubic-bezier(0.2, 0.0, 0.0, 1.0)`  
- No bounce  
- No overshoot  

## Micro‑Shift
- **2–4px** vertical shift  
- Upward for entry  
- Downward for exit  

## Opacity
- Fade from 0 → 100% on entry  
- Fade from 100% → 0 on exit  

---

# Prohibited Motion

Transitions must never:
- Slide horizontally  
- Slide vertically more than 4px  
- Bounce  
- Parallax  
- Scale  
- Rotate  
- Blur  
- Warp  
- Stretch  

These violate the EndlessOS cinematic doctrine.

---

# Page Entry Transition

Sequence:
1. Identity loads  
2. Page mounts  
3. Fade in (120–150ms)  
4. Micro‑shift upward (2–4px)  

---

# Page Exit Transition

Sequence:
1. Fade out (120–150ms)  
2. Micro‑shift downward (2–4px)  
3. Page unmounts  

---

# Modal Transition

Modals:
- Fade in/out  
- No micro‑shift  
- No slide  
- No scale  

Backdrop:
- 0 → 40% opacity fade  

---

# Wheel Transition

Wheels:
- Fade in/out  
- Micro‑expand (2–4px outward)  
- No rotation  
- No bounce  

---

# System Overlay Transition

Overlays:
- Fade in/out  
- No motion  
- No micro‑shift  

---

# Anti‑Patterns

Transitions must never:
- Change based on platform  
- Change based on page type  
- Change based on user behavior  
- Use platform accent colors  
- Use identity‑specific motion  
- Cause layout shift  

---

# Summary

Navigation transitions in EndlessOS are:
- Calm  
- Cinematic  
- Deterministic  
- Identity‑neutral  
- Non‑adaptive  

They reinforce clarity and spatial understanding without ever distracting from content.
