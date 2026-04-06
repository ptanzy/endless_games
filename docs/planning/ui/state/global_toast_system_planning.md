# EndlessOS — Global Toast System Planning

## Purpose
Global Toasts are brief, non‑blocking notifications that communicate:
- Success  
- Failure  
- Warnings  
- System events  
- Background actions  

Toasts must remain:
- Cinematic  
- Deterministic  
- Non‑intrusive  
- Identity‑neutral  
- Platform‑agnostic  

This document defines the global toast system for EndlessOS.

---

# Core Philosophy

## 1. Toasts Must Never Interrupt the User
Toasts:
- Do not block interaction  
- Do not require dismissal  
- Do not freeze UI  
- Do not steal focus  

They are **informational**, not interactive.

---

## 2. Toasts Must Be Deterministic
Toasts must:
- Always appear in the same location  
- Always use the same motion  
- Always follow the same timing  
- Never adapt based on context  

Predictability is mandatory.

---

# Toast Placement

Toasts appear:
- Bottom‑center of the screen  
- Above safe zone  
- Above platform content  
- Below modals and wheels  

Multiple toasts stack upward.

---

# Toast Types

### 1. Success Toasts
- Green neutral tone  
- Short confirmation  

### 2. Error Toasts
- Red neutral tone  
- Clear failure message  

### 3. Warning Toasts
- Yellow neutral tone  
- Non‑critical caution  

### 4. Info Toasts
- Neutral tone  
- General updates  

---

# Visibility Rules

## Duration
- 2.5–3.5 seconds  
- Fixed per OS version  

## Auto‑Dismiss
Toasts auto‑dismiss unless:
- User hovers (desktop)  
- User focuses (keyboard)  

## Manual Dismiss (optional)
- Small “X” icon  
- Only for error/warning toasts  

---

# Motion Rules

Allowed:
- 120–150ms fade  
- 2–4px upward micro‑shift  

Prohibited:
- Slide  
- Bounce  
- Parallax  
- Scale  
- Rotation  

Toasts must feel calm and premium.

---

# Interaction Rules

Toasts must:
- Never steal focus  
- Never block clicks  
- Never block scroll  
- Never overlap modals  

Hover:
- Pauses timer  

Focus:
- Pauses timer  

Touch:
- Tap outside does nothing  
- Toast auto‑dismisses normally  

---

# Accessibility

- Toasts must be announced via screen reader  
- Toasts must not trap focus  
- Toasts must not require interaction  
- Toasts must be dismissible via keyboard  

---

# Anti‑Patterns

Toasts must never:
- Contain actions  
- Contain links  
- Contain long text  
- Contain scrolling content  
- Use platform identity  
- Use accent colors  
- Persist indefinitely  
- Animate aggressively  

---

# Summary

Global Toasts provide brief, non‑blocking feedback that enhances clarity without disrupting flow.  
They must remain cinematic, deterministic, and identity‑neutral across all platforms.
