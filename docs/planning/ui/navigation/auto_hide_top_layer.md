# EndlessOS — Auto‑Hide Top Layer Specification

## Purpose
The Auto‑Hide Top Layer system ensures that the EndlessOS top‑level navigation elements remain:
- Available when needed  
- Invisible when not needed  
- Cinematic and unobtrusive  
- Deterministic and predictable  

This system applies to:
- The utility navigation bar  
- The profile photo + radial wheel  
- The utility mini‑carousel  
- The top‑layer identity elements  

The goal is to preserve maximum screen real estate and maintain a calm, cinematic presentation while still providing fast access to global utilities.

---

# Core Philosophy

## 1. The Top Layer Is Not Always Visible
The top layer is **not** a persistent navigation bar.  
It is a **summonable layer** that appears when needed and disappears when idle.

This preserves:
- Cinematic immersion  
- Content‑first presentation  
- Minimal visual noise  

---

## 2. The Top Layer Must Never Shift Layout
The top layer floats above the layout.

This means:
- No reflow  
- No content push  
- No layout shift  
- No dynamic resizing  

The underlying page must remain perfectly still.

---

## 3. The Top Layer Must Be Predictable
The auto‑hide behavior must:
- Always follow the same timing  
- Always follow the same motion  
- Never adapt based on content  
- Never behave differently per platform  

Determinism builds trust.

---

# Components Affected

The auto‑hide system controls the visibility of:

### 1. Profile Photo + Radial Wheel  
Your global identity anchor.

### 2. Utility Navigation Bar  
Single‑utility icons + multi‑utility wheel triggers.

### 3. Utility Mini‑Carousel  
Global utility pages (Settings, Account, Legal, Support, etc.).

### 4. Top‑Layer Identity Elements  
Any future global tools (e.g., notifications, quick actions).

All of these are considered part of the **Top Layer**.

---

# Visibility Rules

## 1. Initial Visibility
The top layer is visible:
- Immediately upon page load  
- Immediately after navigation  
- Immediately after any modal closes  

This ensures orientation and discoverability.

---

## 2. Auto‑Hide Timer
If the user does not interact with the top layer, it auto‑hides after:

**10–20 seconds**  
(Exact value determined by UX tuning, but must be fixed and deterministic.)

The timer resets when:
- The user moves the mouse within the top 120px of the screen  
- The user interacts with any top‑layer element  
- A modal closes  
- A radial wheel closes  

---

## 3. Summoning the Top Layer
The top layer reappears when:
- The user moves the mouse to the top 120px of the screen  
- The user presses a keyboard shortcut (optional future feature)  
- A system event requires it (e.g., update available)  

Summoning must:
- Fade in  
- Never shift layout  
- Never animate aggressively  

---

# Motion Rules

The top layer uses a **subtle fade**:

- Fade in: 120–150ms  
- Fade out: 120–150ms  
- No slide  
- No bounce  
- No parallax  
- No scale  
- No rotation  

The top layer must feel calm and cinematic.

---

# Interaction Rules

## Hover
Hover over any top‑layer element:
- Cancels auto‑hide  
- Keeps the layer visible  
- Allows radial wheels to expand  

## Focus
Keyboard focus on any top‑layer element:
- Cancels auto‑hide  
- Keeps the layer visible  

## Touch
Touch interactions:
- Tap to summon  
- Tap outside to hide  
- Must not require hover  

---

# Radial Wheel Integration

Radial wheels (profile wheel + utility wheels) must:
- Only expand when the top layer is visible  
- Keep the top layer visible while open  
- Reset the auto‑hide timer on open  
- Reset the auto‑hide timer on close  

If the top layer is hidden:
- Moving the mouse to the top summons it  
- THEN the wheel can be triggered  

This prevents accidental wheel activation.

---

# Safe Zone Compliance

The top layer must:
- Always remain inside safe zones  
- Never clip  
- Never touch screen edges  
- Never overlap critical UI  

When hidden:
- It must fully disappear (opacity 0)  
- It must not leave behind interactive remnants  

---

# States

The top layer has **three states**:

### 1. Visible  
- Full opacity  
- Interactive  
- Wheels can open  

### 2. Fading Out  
- Opacity decreasing  
- Still interactive until fully hidden  

### 3. Hidden  
- Opacity 0  
- Non‑interactive  
- Summoned by mouse movement  

---

# Anti‑Patterns

The following violate the auto‑hide doctrine:

- Sliding the top layer off‑screen  
- Shrinking or compressing the top layer  
- Adaptive timing  
- Platform‑specific behavior  
- Hover‑dependent required information  
- Layout shift  
- Parallax or bounce animations  
- Leaving the top layer partially visible  
- Delayed summoning  

These are strictly prohibited.

---

# Summary

The Auto‑Hide Top Layer system ensures EndlessOS maintains a cinematic, content‑first experience while still providing fast access to global utilities.

The top layer:
- Appears when needed  
- Disappears when idle  
- Never shifts layout  
- Never uses platform identity  
- Never animates aggressively  
- Always respects safe zones  

This system keeps EndlessOS clean, calm, and future‑proof.
