# EndlessOS — Layout System Overview

## Purpose
The EndlessOS Layout System Overview provides a high‑level map of how all layout‑related doctrines, rules, and specifications fit together.  
It defines the structural logic of the platform, the relationships between layout components, and the principles that ensure deterministic, cinematic, content‑first UI across all pages.

This document sits directly beneath:
- layout_design_doctrine.md  

And above:
- hub_layout_spec.md  
- platform_page_layout_spec.md  
- utility_page_layout_spec.md  
- safe_zone_rules.md  
- tooltip_spec.md  

---

# System Goals

The EndlessOS layout system is designed to:
- Maintain deterministic structure  
- Support cinematic, console‑grade presentation  
- Prioritize content over UI  
- Scale across platforms (Games, Tube, Music, Books, Events)  
- Support mouse, keyboard, and touch without requiring hover  
- Provide optional clarity through tooltips  
- Enforce safe zones and spacing rules  
- Prevent layout shift and unpredictable behavior  

The layout system is the backbone of the EndlessOS experience.

---

# System Architecture

The layout system is composed of **five structural layers**:

1. **Global Frame**  
2. **Safe Zones**  
3. **Grid System**  
4. **Page Types**  
5. **Interaction Layer (Hover, Focus, Tooltips)**  

Each layer is deterministic and inherits from the layout doctrine.

---

# 1. Global Frame

The global frame defines the universal structure of every page:

- Top navigation (global or platform)  
- Safe zone boundaries  
- Content region  
- Optional sidebar (platform‑specific)  
- Footer spacing  

The global frame:
- Never changes based on content  
- Never collapses or expands dynamically  
- Never shifts during interaction  

It is the skeleton of EndlessOS.

---

# 2. Safe Zones

Safe zones ensure:
- No clipped content  
- No edge collisions  
- No unreadable text  
- No controller‑navigation traps  
- No hover‑triggered flicker near edges  

Safe zones are:
- Fixed per breakpoint  
- Non‑negotiable  
- Inherited by all page types  
- Required for tooltip placement  

Safe zones are defined in `safe_zone_rules.md`.

---

# 3. Grid System

EndlessOS uses a **3/2/1 responsive grid**:

- **Large screens:** 3 columns  
- **Medium screens:** 2 columns  
- **Small screens:** 1 column  

Rules:
- No masonry  
- No staggered heights  
- No overlapping content  
- No dynamic resizing  
- No content‑driven layout changes  

The grid ensures clarity, predictability, and cinematic composition.

---

# 4. Page Types

EndlessOS defines three page types:

## A. Hub Pages
- High‑level discovery  
- Large cards  
- Wide spacing  
- Cinematic presentation  

## B. Platform Pages
- Games, Tube, Music, Books, Events  
- Inherit global layout  
- Apply platform identity (accent + background)  
- Maintain structural consistency  

## C. Utility Pages
- Settings, Account, Legal, etc.  
- Higher density  
- Text‑driven  
- Smaller cards  

Each page type has its own spec file.

---

# 5. Interaction Layer

The interaction layer defines how layout responds to:

- Hover  
- Focus  
- Touch  
- Tooltips  

### Hover
Allowed for:
- Tooltips  
- Subtle emphasis  

Hover must never:
- Reveal required information  
- Shift layout  
- Animate aggressively  

### Focus
Must:
- Follow predictable order  
- Never trap the user  
- Never cause layout shift  

### Touch
Must:
- Avoid hover‑dependent UI  
- Use large targets  
- Respect safe zones  

### Tooltips
Defined in `tooltip_spec.md`.

Tooltips:
- Are supplemental  
- Never contain required information  
- Never shift layout  
- Use subtle fade  
- Respect safe zones  

---

# Layout System Flow

The layout system flows top‑down:
layout_design_doctrine.md
↓
layout_system_overview.md
↓

↓ hub_layout_spec.md
↓ platform_page_layout_spec.md
↓ utility_page_layout_spec.md
↓ safe_zone_rules.md
↓ tooltip_spec.md

This ensures:
- Doctrine → Overview → Specifics  
- No contradictions  
- No ad‑hoc layout decisions  
- No platform‑specific hacks  

---

# Anti‑Patterns

The layout system prohibits:
- Dynamic layout changes  
- Content‑driven resizing  
- Masonry grids  
- Overlapping elements  
- Edge‑to‑edge content  
- Layout shift during interaction  
- Hover‑only essential information  
- Tooltip‑dependent UI  
- Platform‑specific layout hacks  

These violate the deterministic nature of EndlessOS.

---

# Summary

The EndlessOS layout system is a deterministic, cinematic, content‑first architecture.  
It uses a stable global frame, strict safe zones, a predictable grid, and optional tooltips to create a modern, gaming‑grade layout that scales across all platforms.

This overview defines how all layout components relate to each other and ensures long‑term structural consistency across EndlessOS.
