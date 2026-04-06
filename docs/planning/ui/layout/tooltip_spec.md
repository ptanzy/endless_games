# EndlessOS — Tooltip Specification

## Purpose
The EndlessOS tooltip system defines how tooltips behave, appear, and integrate into the platform.  
Tooltips provide optional clarity without becoming a dependency, ensuring the UI remains clean, cinematic, and deterministic.

This document defines:
- Tooltip purpose  
- Trigger behavior  
- Timing  
- Motion  
- Placement  
- Styling  
- Accessibility  
- Anti‑patterns  

Tooltips are supplemental and must never contain required information.

---

# Core Principles

## 1. Supplemental, Not Required
Tooltips may enhance clarity, but they must never:
- Contain required information  
- Be the only way to understand an action  
- Block interaction  
- Replace labels where labels are needed  

Tooltips are optional helpers, not core UI.

---

## 2. Non‑Intrusive
Tooltips must:
- Never shift layout  
- Never push content  
- Never overlap critical UI  
- Never animate aggressively  

They must feel calm and cinematic.

---

## 3. Deterministic Behavior
Tooltip behavior must be:
- Predictable  
- Consistent  
- Stable  
- Non‑adaptive  

No dynamic repositioning unless required to avoid clipping.

---

# Trigger Behavior

## Hover Trigger
Tooltips appear on hover after a short delay:
- **Delay:** 150–200ms  
- **Exit:** 100ms fade out  

Hover must not:
- Reveal required information  
- Trigger layout changes  

## Focus Trigger
Tooltips appear on keyboard focus:
- Same delay as hover  
- Same fade behavior  

Focus tooltips ensure accessibility without requiring hover.

---

# Motion

Tooltip motion must be:
- Subtle  
- Calm  
- Predictable  

Allowed:
- Opacity fade (120–150ms)  

Prohibited:
- Slide  
- Bounce  
- Elastic  
- Scale  
- Parallax  
- Morphing  

Tooltips must never draw attention to themselves.

---

# Placement

Tooltips may appear:
- Above the element  
- Below the element  
- Left or right (fallback)  

Rules:
- Prefer above  
- Avoid clipping  
- Maintain safe zones  
- Never overlap the cursor  
- Never cover critical UI  

---

# Styling

Tooltips use:
- Neutral background (`gray-800`)  
- Neutral text (`gray-200`)  
- 12px Inter  
- 8px padding  
- 4px corner radius  
- 1px neutral border (`gray-700`)  

Tooltips must never:
- Use accent colors  
- Use platform colors  
- Use semantic colors  
- Use shadows larger than 2px  
- Use decorative gradients  

---

# Accessibility

Tooltips must:
- Be accessible via keyboard focus  
- Not trap focus  
- Not require hover  
- Not contain required information  
- Not interfere with screen readers  

Screen readers may ignore tooltips unless explicitly marked as helpful metadata.

---

# Anti‑Patterns

The following are strictly prohibited:
- Tooltips containing required information  
- Tooltips that shift layout  
- Tooltips that animate aggressively  
- Tooltips that use accent colors  
- Tooltips that use semantic colors  
- Tooltips that appear instantly  
- Tooltips that flicker  
- Tooltips that cover essential UI  
- Tooltips that depend on hover only  

These violate the EndlessOS tooltip philosophy.

---

# Summary

EndlessOS tooltips are calm, supplemental, and deterministic.  
They enhance clarity without becoming a dependency, using subtle motion, neutral styling, and predictable behavior across all platforms and input methods.
