# EndlessOS — Color System

## Purpose
The EndlessOS color system defines how color is used across the platform.  
It establishes a neutral, cinematic foundation that prioritizes clarity, identity, and long‑term maintainability.  
This document explains the rules, constraints, and behaviors of color within the EndlessOS UI.

---

## Scope
This document covers:
- Neutral gray hierarchy  
- Global accent model (Blue + Red)  
- Platform‑level accent overrides  
- Dual‑accent loading wheel behavior  
- Semantic color rules  
- Identity vs. function  
- Behavioral constraints  
- Anti‑patterns  
- Future expansion  

It does not define exact color tokens or palette values.  
Those will be introduced in a future specification document.

---

# Core Principles

## 1. Neutral First
EndlessOS is built on a foundation of gaming‑grade neutral grays.  
These neutrals define:
- Structure  
- Hierarchy  
- Depth  
- Surfaces  
- Navigation  
- Cards and panels  

Neutrals are the backbone of the UI.  
They ensure calmness, readability, and consistency across all platforms.

---

## 2. Accents Are Identity, Not Function
Accent colors represent **platform identity only**.  
They are intentionally rare and must never be used to communicate:
- Action  
- State  
- Hierarchy  
- Navigation  
- Focus  
- Selection  

Accents appear only in:
- Platform identity bars  
- Platform‑specific decorative elements  
- Platform‑specific progress indicators  
- Platform loading mask wheel  
- Rare, intentional identity moments  

Accents must never appear in:
- Icons  
- Buttons (except platform‑identity banners)  
- Active states  
- Structural surfaces  
- Focus rings  
- Typography  
- Navigation elements  

Accents are not functional colors.  
They are identity markers.

---

## 3. Semantic Colors Override Everything
Semantic colors communicate meaning across the entire OS.  
They are universal and platform‑agnostic.

### Semantic Color Roles
- **Success** → Green  
- **Warning** → Yellow  
- **Error** → Red  
- **Play / Start** → Green  
- **Stop / End** → Red  

Semantic colors always override:
- Platform accents  
- Neutral hierarchy  
- Background identity  

Semantic colors must be used sparingly and consistently.

---

# Global Accent Model

EndlessOS defines a **global accent set** consisting of:

- **Blue** — primary global accent  
- **Red** — secondary global accent  

These accents are available across all platforms and surfaces unless explicitly overridden by a platform.

### Platform Overrides
Platforms may define their own accent color.  
When a platform provides an override:
- The platform accent replaces the global accent set  
- All identity surfaces inside that platform use the platform accent  
- Semantic colors still override platform accents  

If a platform does **not** override, it inherits the global Blue + Red accents.

### Dual‑Accent Loading Wheel
The loading wheel is one of the few UI elements where multi‑accent expression is allowed.  
It may use:
- Blue + Red alternating segments  
- Blue outer ring + Red inner ring  
- Blue → Red sequential pulses  

This is a non‑interactive, identity‑driven element and does not communicate state.

---

# Color Layers

## 1. Structural Layer (Neutrals)
Used for:
- Backgrounds  
- Panels  
- Cards  
- Navigation surfaces  
- Modals  
- Utility layers  

Neutrals define the spatial and visual hierarchy of the OS.

---

## 2. Identity Layer (Accents)
Used for:
- Platform identity  
- Platform backgrounds  
- Platform progress indicators  
- Platform loading mask wheel  

Accents never indicate action or state.

---

## 3. Semantic Layer
Used for:
- Errors  
- Warnings  
- Success states  
- Play/Stop actions  
- Critical system feedback  

Semantic colors are universal and override all other layers.

---

# Behavioral Rules

## 1. Buttons
- Default buttons use neutral grays  
- Accent buttons are almost never allowed  
- Semantic buttons override everything  
- Buttons must not use accent colors unless they are platform‑identity banners  

Buttons communicate action, not identity.

---

## 2. Icons
Icons must always use neutral grays.  
Icons must never use:
- Accent colors  
- Semantic colors (except in rare, explicit semantic icon cases)  

Icons communicate function, not identity.

---

## 3. Active States
Active states use neutral variations only:
- Slightly brighter gray  
- Slightly elevated surface  
- Slightly thicker outline  

Active states must never use accent colors.

---

## 4. Focus States
Focus rings must:
- Use neutral or semantic colors  
- Never use accent colors  
- Never use gradients  
- Never use animated color shifts  

Focus must be clear, predictable, and accessible.

---

## 5. Backgrounds
Backgrounds must:
- Use neutral grays  
- Use platform backgrounds only when inside a platform  
- Never use accent colors as structural surfaces  

Backgrounds must remain calm and cinematic.

---

# Anti‑Patterns
The following are not allowed:
- Accent‑colored icons  
- Accent‑colored buttons (except identity banners)  
- Accent‑colored active states  
- Accent‑colored focus rings  
- Accent‑colored structural surfaces  
- Using accents to indicate selection  
- Using accents to indicate hierarchy  
- Using accents for navigation  
- Color‑changing UI based on content  
- Warm neutrals  
- Decorative gradients  
- Overly saturated UI  
- Color‑driven meaning outside semantic roles  

These violate the clarity and identity of the EndlessOS color system.

---

# Future Expansion
The following will be defined in a future specification document:
- Exact neutral gray palette  
- Exact accent palette (global + platform overrides)  
- Exact semantic color tokens  
- Light/dark mode behavior  
- Color accessibility rules  
- Color contrast ratios  
- Color tokens and naming conventions  

These are intentionally deferred until the core UI is implemented.

---

# Summary
The EndlessOS color system is neutral, identity‑driven, and deterministic.  
It uses accents sparingly, neutrals consistently, and semantic colors intentionally.  
This system ensures clarity, calmness, and long‑term maintainability across the entire platform.
