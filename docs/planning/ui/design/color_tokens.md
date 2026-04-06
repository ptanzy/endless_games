# EndlessOS — Color Tokens

## Purpose
This document defines the official EndlessOS color tokens.  
These tokens represent the **exact palette values** used across the OS and serve as the foundation for all UI surfaces, components, and platform‑level overrides.

This file is the authoritative source for:
- Neutral gray scale  
- Global accent colors (Blue + Red)  
- Semantic colors  
- Text colors  
- Focus colors  
- Shadows  
- Token naming conventions  

Platform‑specific accent overrides may extend this file but must not modify global tokens.

---

# Token Naming Conventions

Tokens follow a strict naming pattern:

<category>-<name>-<scale>

Code

Examples:
- `gray-700`
- `accent-blue-500`
- `semantic-error`
- `text-secondary`

### Categories
- `gray` → Neutral structural palette  
- `accent` → Identity accents (global or platform‑specific)  
- `semantic` → Meaning‑driven colors  
- `text` → Typography colors  
- `focus` → Focus ring colors  
- `shadow` → Elevation shadows  

---

# 1. Neutral Gray Scale (Structural Layer)

These neutrals define the core EndlessOS visual hierarchy.  
They are cool‑neutral, gaming‑grade, and optimized for dark‑mode‑first UI.

| Token | Hex | Description |
|-------|------|-------------|
| `gray-0` | `#FFFFFF` | Pure white (text only) |
| `gray-50` | `#F5F6F7` | Ultra‑light neutral (rare) |
| `gray-100` | `#E6E8EA` | Light borders, dividers |
| `gray-200` | `#C8CCD0` | Disabled states, secondary borders |
| `gray-300` | `#A9AFB5` | Secondary text |
| `gray-400` | `#8A929A` | Tertiary text |
| `gray-500` | `#6B757F` | Icons, inactive UI |
| `gray-600` | `#4D5660` | Cards, low‑elevation surfaces |
| `gray-700` | `#363D44` | Panels, navigation surfaces |
| `gray-800` | `#1F2428` | Primary background |
| `gray-900` | `#0F1113` | Cinematic black, deep background |

---

# 2. Global Accent Colors (Identity Layer)

EndlessOS defines two global accent colors.  
These are used across the OS unless overridden by a platform.

## Blue Accent (Primary Global Accent)
| Token | Hex |
|-------|------|
| `accent-blue-500` | `#3B82F6` |
| `accent-blue-600` | `#2563EB` |
| `accent-blue-700` | `#1D4ED8` |

## Red Accent (Secondary Global Accent)
| Token | Hex |
|-------|------|
| `accent-red-500` | `#EF4444` |
| `accent-red-600` | `#DC2626` |
| `accent-red-700` | `#B91C1C` |

### Accent Usage Rules
- Accents are identity‑only  
- Never used for functional UI  
- Never used for icons, buttons, focus rings, or active states  
- May be overridden at the platform level  
- If no override exists, platforms inherit Blue + Red  

---

# 3. Dual‑Accent Loading Wheel Tokens

The loading wheel is one of the few UI elements allowed to use multiple accents.

| Token | Hex | Usage |
|--------|------|--------|
| `accent-blue-spinner` | `#3B82F6` | Spinner segment |
| `accent-red-spinner` | `#EF4444` | Spinner segment |

These two colors may be used:
- Alternating  
- Sequentially pulsing  
- Inner/outer ring pairing  

---

# 4. Semantic Colors (Meaning Layer)

Semantic colors override all other layers, including accents.

| Role | Token | Hex |
|------|--------|------|
| Success | `semantic-success` | `#22C55E` |
| Warning | `semantic-warning` | `#FACC15` |
| Error | `semantic-error` | `#EF4444` |
| Play/Start | `semantic-play` | `#22C55E` |
| Stop/End | `semantic-stop` | `#EF4444` |

Notes:
- Red is shared between error + stop  
- Green is shared between success + play  
- Yellow is reserved for warnings only  

---

# 5. Text Colors

| Token | Hex | Usage |
|--------|------|--------|
| `text-primary` | `#FFFFFF` | Main text |
| `text-secondary` | `#C8CCD0` | Secondary text |
| `text-tertiary` | `#8A929A` | Tertiary text |
| `text-inverse` | `#0F1113` | Text on light surfaces (rare) |

---

# 6. Focus & Outline Colors

| Token | Hex | Usage |
|--------|------|--------|
| `focus-ring` | `#3B82F6` | Neutral, accessible focus ring |
| `outline-neutral` | `#A9AFB5` | Neutral outlines |

Focus rings must never use accent colors other than the neutral blue defined above.

---

# 7. Shadows & Elevation

| Token | Value | Usage |
|--------|--------|--------|
| `shadow-1` | rgba(0,0,0,0.25) | Light elevation |
| `shadow-2` | rgba(0,0,0,0.40) | Medium elevation |
| `shadow-3` | rgba(0,0,0,0.60) | High elevation |

---

# 8. Platform Accent Overrides

Platforms may define their own accent color.  
When a platform provides an override:

- The platform accent replaces the global Blue + Red  
- All identity surfaces inside that platform use the platform accent  
- Semantic colors still override platform accents  
- Neutral grays remain unchanged  

Platform overrides must follow the same token naming pattern:

accent-<platform>-500
accent-<platform>-600
accent-<platform>-700

Code

Example:
accent-games-500
accent-games-600
accent-games-700

Code

---

# 9. Future Expansion

The following will be added in future revisions:

- Light mode variants  
- Extended accent palettes  
- Platform‑specific accent sets  
- Accessibility contrast mapping  
- Color‑driven motion tokens  
- Theming API tokens  

---

# Summary

This document defines the complete EndlessOS color token system.  
These tokens form the foundation of the platform’s visual identity and ensure consistency, clarity, and long‑term maintainability across all UI surfaces.