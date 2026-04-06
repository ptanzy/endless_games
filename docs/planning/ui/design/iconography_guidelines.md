# EndlessOS — Iconography Guidelines

## Purpose
The EndlessOS iconography system defines how icons are designed, styled, and applied across the platform.  
Icons are functional, not decorative. They communicate meaning with clarity, consistency, and zero ambiguity.

This document outlines:
- Icon style and geometry  
- Stroke and fill rules  
- Color usage  
- Size and alignment  
- Platform‑level overrides  
- Behavioral constraints  
- Anti‑patterns  

Component‑level icon usage will be defined in a future specification.

---

# Core Principles

## 1. Functional, Not Decorative
Icons exist to:
- Communicate function  
- Reinforce hierarchy  
- Improve scannability  

Icons must never:
- Express identity  
- Decorate surfaces  
- Convey emotion  
- Use accent colors  

Icons are tools, not branding.

---

## 2. Deterministic Geometry
Icons must follow a strict geometric system:
- Consistent stroke weight  
- Consistent corner radius  
- Consistent visual balance  
- Consistent optical alignment  

No icon may deviate from the system.

---

## 3. Neutral, Calm, Cinematic
Icons must blend into the EndlessOS neutral UI.  
They must never compete with content or platform identity.

Icons use:
- Neutral grays only  
- No accent colors  
- No semantic colors (except explicit semantic icons)  

---

# Icon Style

## Stroke Style
EndlessOS uses a **2px geometric stroke** for all icons.

### Rules:
- Stroke weight: **2px**  
- Stroke caps: **Round**  
- Stroke joins: **Round**  
- No variable stroke widths  
- No tapered strokes  
- No calligraphic strokes  

This creates a clean, modern, gaming‑grade look.

---

## Corner Radius
Icons must use consistent rounding:
- Outer corners: **2px radius**  
- Inner corners: **1–2px radius** depending on geometry  

No sharp, unrounded corners unless the shape demands it (e.g., a square icon).

---

## Fill Rules
Icons may be:
- **Stroke‑only** (default)  
- **Stroke + minimal fill** (rare, for clarity)  

Icons must never be:
- Fully filled silhouettes  
- Heavy, bold, or blocky  
- Overly detailed  

Icons must remain lightweight and readable at small sizes.

---

# Color Usage

Icons must use **neutral grays only**:

| Token | Hex | Usage |
|--------|------|--------|
| `gray-500` | `#6B757F` | Default icon color |
| `gray-400` | `#8A929A` | Secondary icons |
| `gray-300` | `#A9AFB5` | Disabled icons |

### Strict Prohibitions:
- No accent colors  
- No platform colors  
- No gradients  
- No semantic colors (except explicit semantic icons)  
- No color‑changing icons based on content  

Icons must remain neutral and functional.

---

# Icon Sizes

EndlessOS uses a fixed icon size system:

| Size | Usage |
|-------|--------|
| **16px** | Dense UI, metadata, lists |
| **20px** | Default UI icon size |
| **24px** | Navigation, toolbars |
| **32px** | Large buttons, hero UI |
| **48px** | Platform landing screens (rare) |

### Rules:
- Icons must be pixel‑perfect at all sizes  
- No scaling icons dynamically  
- No fractional pixel rendering  
- No stretching or distortion  

---

# Alignment & Optical Balance

Icons must be optically centered within their bounding box.

### Alignment Rules:
- Align to a **20px grid** for default UI  
- Maintain consistent visual weight  
- Avoid asymmetry unless semantically required  
- Use optical adjustments for diagonal shapes  

Icons must feel stable and balanced.

---

# Semantic Icons

Semantic icons are the **only** icons allowed to use semantic colors.

| Role | Color | Example Icons |
|------|--------|----------------|
| Error | `semantic-error` | Error, alert, stop |
| Warning | `semantic-warning` | Warning, caution |
| Success | `semantic-success` | Check, success |
| Play/Start | `semantic-play` | Play button |
| Stop/End | `semantic-stop` | Stop button |

### Rules:
- Semantic icons must be stroke‑based  
- No filled semantic icons  
- No decorative semantic icons  

Semantic icons communicate meaning, not identity.

---

# Platform Overrides

Platforms may not override:
- Icon style  
- Stroke weight  
- Geometry  
- Color rules  
- Size system  

Platforms may override:
- Icon *sets* (e.g., Games may have game‑specific icons)  
- Display‑level icons (hero screens only)  

Platform overrides must:
- Follow all EndlessOS icon rules  
- Maintain stroke weight  
- Maintain geometry  
- Maintain color neutrality  

Icons remain a system‑level asset.

---

# Behavioral Rules

## 1. No Animated Icons
Icons must not:
- Spin  
- Pulse  
- Bounce  
- Morph  
- Glow  
- Color‑shift  

Motion belongs to the motion system, not iconography.

---

## 2. No Decorative Icons
Icons must not:
- Use accent colors  
- Use platform colors  
- Use gradients  
- Use shadows  
- Use outlines  
- Use 3D effects  
- Use textures  

Icons must remain flat, neutral, and functional.

---

## 3. No Dynamic Icons
Icons must not change based on:
- Content  
- Theme  
- Platform  
- User behavior  

Icons must remain stable and predictable.

---

# Anti‑Patterns

The following are not allowed:
- Filled icons  
- Accent‑colored icons  
- Platform‑colored icons  
- Inconsistent stroke weights  
- Overly detailed icons  
- Photographic icons  
- Emoji‑style icons  
- Dynamic or animated icons  
- Icons that break the grid  
- Icons that use shadows or gradients  

These violate the clarity and identity of the EndlessOS icon system.

---

# Future Expansion

Future documents will define:
- Component‑level icon usage  
- Platform‑specific icon packs  
- Iconography for motion transitions  
- Accessibility icon variants  
- Iconography for controller vs. touch vs. mouse input  

---

# Summary

The EndlessOS iconography system is neutral, geometric, and gaming‑grade.  
Icons use a strict 2px stroke, neutral grays, and deterministic geometry.  
They are functional, not decorative, ensuring clarity and long‑term maintainability across the entire platform.
