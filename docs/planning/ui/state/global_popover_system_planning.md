# EndlessOS — Global Popover System Planning

## Purpose
Global Popovers are lightweight, contextual UI surfaces that provide:
- Micro‑information  
- Micro‑actions  
- Inline utility access  
- Non‑blocking contextual UI  

Popovers must remain:
- Deterministic  
- Non‑modal  
- Non‑blocking  
- Cinematic  
- Identity‑neutral  
- Platform‑agnostic  

This document defines the global popover system for EndlessOS.

---

# Core Philosophy

## 1. Popovers Are Not Modals
Popovers:
- Do not block interaction  
- Do not dim the background  
- Do not freeze the page  
- Do not require dismissal before navigation  

They are **contextual helpers**, not decision gates.

---

## 2. Popovers Must Be Deterministic
Popovers must:
- Always appear in the same position relative to their anchor  
- Always use the same motion  
- Always use the same safe‑zone rules  
- Never adapt based on content  

Predictability is mandatory.

---

## 3. Popovers Must Never Shift Layout
Popovers float above content.

They must never:
- Push content  
- Resize content  
- Cause reflow  
- Affect scroll position  

---

# Popover Types

### 1. Informational Popovers
- Short text  
- Tooltips  
- Descriptions  

### 2. Action Popovers
- Small sets of actions (2–4 max)  
- Quick utility actions  

### 3. Hybrid Popovers (future)
- Micro‑content + micro‑actions  

---

# Visibility Rules

## 1. Popovers Appear When:
- Hovering over an anchor (desktop)  
- Focusing an anchor (keyboard)  
- Tapping an anchor (touch)  
- Triggering a utility icon  

## 2. Popovers Hide When:
- Mouse leaves anchor  
- Focus leaves anchor  
- User taps outside  
- User scrolls  
- User navigates  
- A modal opens  
- A wheel opens  

Popovers must never persist across navigation.

---

# Motion Rules

Allowed:
- 120–150ms fade  
- 2–4px micro‑shift  

Prohibited:
- Slide  
- Bounce  
- Parallax  
- Scale  
- Rotation  

Motion must be calm and cinematic.

---

# Safe Zone Rules

Popovers must:
- Stay fully inside safe zones  
- Flip sides if needed  
- Never clip screen edges  
- Never resize to fit  

If space is insufficient:
- Popover repositions  
- Content scrolls internally  

---

# Interaction Rules

## Hover
- Shows popover  
- Hides on exit  

## Focus
- Shows popover  
- Hides on blur  

## Touch
- Tap to show  
- Tap outside to hide  

## Controller (future)
- Radial directional navigation  
- Snap to nearest anchor  

---

# Accessibility

- Popovers must be announced  
- Popover content must be reachable via keyboard  
- Popovers must close on Escape  
- Popovers must not trap focus  

---

# Anti‑Patterns

Popovers must never:
- Block interaction  
- Replace modals  
- Replace toasts  
- Contain long content  
- Contain scrolling lists  
- Use platform identity  
- Use accent colors  
- Animate aggressively  

---

# Summary

Global Popovers are lightweight, contextual UI surfaces that enhance clarity without disrupting flow.  
They must remain deterministic, cinematic, and non‑blocking across all platforms and utilities.
