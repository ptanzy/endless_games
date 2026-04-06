# EndlessOS — Utility Layer Visibility Rules

## Purpose
The Utility Layer is the collection of **global utility surfaces** that sit above platform content but below modals and system overlays.  
This includes:

- Utility Navigation Bar  
- Utility Mini‑Carousel  
- Utility Modals  
- Utility Popovers  
- Utility Quick Actions (future)  

This document defines **when the utility layer is visible**, **when it hides**, **what triggers visibility**, and **how it interacts with the auto‑hide top layer**.

---

# Core Philosophy

## 1. The Utility Layer Is Not Persistent
The utility layer is **summonable**, not always visible.  
It appears when needed and hides when idle.

This preserves:
- Cinematic immersion  
- Content‑first presentation  
- Minimal visual noise  

---

## 2. The Utility Layer Must Never Shift Layout
The utility layer floats above the page.

It must never:
- Push content  
- Resize content  
- Cause reflow  
- Change page layout  

It is a **non‑layout surface**.

---

## 3. Visibility Must Be Deterministic
The utility layer must:
- Always appear under the same conditions  
- Always hide under the same conditions  
- Never adapt based on context  
- Never behave differently per platform  

Predictability is mandatory.

---

# Utility Layer Components

The Utility Layer includes:

### 1. Utility Navigation Bar  
Global icons for Settings, Account, Wallet, Legal, Support, etc.

### 2. Utility Mini‑Carousel  
Scrollable list of utility pages.

### 3. Utility Modals  
Quick‑action system modals (sign out, quick settings, etc.).

### 4. Utility Popovers  
Small contextual utility surfaces (future).

### 5. Utility Quick Actions (future)  
Fast toggles and micro‑tools.

All follow the same visibility rules.

---

# Visibility Rules

## 1. Visible on Page Load
The utility layer is visible:
- Immediately after navigation  
- Immediately after platform entry  
- Immediately after modal close  
- Immediately after wheel close  

This ensures orientation and discoverability.

---

## 2. Auto‑Hide Timer
If the user does not interact with the utility layer, it auto‑hides after:

**10–20 seconds**  
(Exact value fixed per OS version.)

The timer resets when:
- The user moves the mouse into the top 120px  
- The user interacts with any utility element  
- A modal closes  
- A radial wheel closes  

---

## 3. Summoning the Utility Layer
The utility layer reappears when:
- The user moves the mouse to the top 120px  
- The user opens the profile radial wheel  
- The user opens a utility modal  
- A system event requires it (e.g., update available)  

Summoning must:
- Fade in  
- Never shift layout  
- Never animate aggressively  

---

# Interaction Behavior

## Hover
Hover over any utility element:
- Cancels auto‑hide  
- Keeps the layer visible  

Hover must not:
- Reveal required information  
- Shift layout  

## Focus
Focus on any utility element:
- Cancels auto‑hide  
- Keeps the layer visible  

## Touch
Touch interactions:
- Tap to summon  
- Tap outside to hide  
- Must not require hover  

---

# Motion Rules

Utility layer uses the same motion rules as the top layer:

Allowed:
- 120–150ms opacity fade  
- 2–4px micro‑shift  

Prohibited:
- Slide  
- Bounce  
- Parallax  
- Scale  
- Rotation  

Motion must support clarity, not personality.

---

# Safe Zone Compliance

The utility layer must:
- Sit fully inside safe zones  
- Never clip  
- Never exceed top safe zone boundaries  
- Never overlap critical UI  

If a utility element would violate safe zones:
- Reduce its internal scroll  
- Never resize the layer  
- Never shift the layer  

---

# Interaction With Other Systems

## 1. Radial Wheels
If a wheel is open:
- Utility layer remains visible  
- Auto‑hide timer pauses  
- Closing the wheel resets the timer  

## 2. Modals
Opening a modal:
- Freezes utility layer visibility  
- Utility layer remains visible behind the modal  
- Auto‑hide timer pauses  

Closing a modal:
- Resets auto‑hide timer  

## 3. Navigation Stack
Navigating to a new page:
- Utility layer becomes visible  
- Auto‑hide timer resets  

## 4. Hub
On the Hub:
- Utility layer behaves identically  
- Auto‑hide still applies  

---

# Anti‑Patterns

The utility layer must never:
- Slide off‑screen  
- Shrink or compress  
- Resize dynamically  
- Shift layout  
- Adapt based on content  
- Use platform identity  
- Use accent colors  
- Animate aggressively  
- Leave partially visible remnants  

These violate the EndlessOS UI doctrine.

---

# Summary

The Utility Layer is a summonable, cinematic, deterministic global surface that provides access to system‑level utilities without disrupting platform content.

It must:
- Appear on load  
- Hide when idle  
- Reappear on demand  
- Never shift layout  
- Never adapt dynamically  
- Always respect safe zones  

This ensures EndlessOS remains calm, predictable, and console‑grade.