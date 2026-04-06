# EndlessOS — Layout Design Doctrine

## Purpose
The EndlessOS layout design doctrine defines the structural philosophy that governs how screens, pages, and components are arranged across the platform.  
It establishes a deterministic, cinematic, content‑first layout system that scales across platforms while maintaining clarity, predictability, and identity isolation.

This document is the root foundation for:
- layout_system_overview.md  
- hub_layout_spec.md  
- platform_page_layout_spec.md  
- utility_page_layout_spec.md  
- safe_zone_rules.md  
- tooltip_spec.md  

All layout specifications inherit from this doctrine.

---

# Core Philosophy

## 1. Deterministic, Never Adaptive
EndlessOS layout must behave the same way every time.

This means:
- No dynamic layout changes based on content  
- No adaptive UI that shifts based on user behavior  
- No unpredictable resizing  
- No collapsing/expanding sections unless explicitly defined  
- No layout recomputation during interaction  

Determinism builds trust and reduces cognitive load.

---

## 2. Content‑First, UI‑Second
The layout must always prioritize:
- Content visibility  
- Content hierarchy  
- Content clarity  

The UI is the frame, not the star.

This means:
- Strong negative space  
- Clear grouping  
- Predictable spacing  
- Minimal ornamentation  
- No decorative layout elements  

---

## 3. Cinematic, Calm, Console‑Grade
EndlessOS layout draws from modern gaming platforms:
- PS5  
- Xbox  
- Steam Big Picture  
- Battle.net  

This means:
- Wide, breathable spacing  
- Stable grids  
- Clear visual anchors  
- No clutter  
- No density spikes  
- No chaotic stacking  

The layout must feel calm and cinematic.

---

## 4. Platform‑Agnostic Structure
The layout system must scale across:
- Games  
- Tube  
- Music  
- Books  
- Events  
- Utility pages  
- Hub surfaces  

Platforms may override:
- Accent color  
- Background identity  
- Display typography  

Platforms may **not** override:
- Grid structure  
- Spacing rules  
- Safe zones  
- Navigation placement  
- Page‑level composition  

Layout is a system‑level asset.

---

## 5. Safe Zones Are Sacred
Safe zones ensure:
- No clipped content  
- No edge collisions  
- No unreadable text on extreme edges  

Safe zones must:
- Be consistent across all pages  
- Never be overridden  
- Never be reduced for “more content”  
- Scale proportionally with breakpoints  

Safe zones are non‑negotiable.

---

## 6. Zero Layout Shift
EndlessOS layout must never shift unexpectedly.

This means:
- No reflow during interaction  
- No content jumping  
- No shifting cards  
- No dynamic height changes  
- No animated layout transitions  

Layout must remain stable and trustworthy.

---

## 7. Tooltips Are Allowed but Non‑Essential
Hover tooltips may appear, but they must:
- Never contain required information  
- Never be the only way to understand an action  
- Never shift layout  
- Never block interaction  
- Never animate aggressively  

Tooltips enhance clarity without affecting layout structure.

---

# Structural Components

## 1. Global Page Frame
Every page in EndlessOS is built on the same structural frame:
- Top navigation (global or platform)  
- Safe zone boundaries  
- Content region  
- Optional sidebar (platform‑specific)  
- Footer spacing  

This frame is immutable.

---

## 2. Grid System
EndlessOS uses a **3/2/1 column responsive grid**:
- Large screens: 3 columns  
- Medium screens: 2 columns  
- Small screens: 1 column  

Rules:
- No masonry layouts  
- No staggered heights  
- No variable‑height cards within the same row  
- No overlapping content  
- No floating elements  

The grid must remain clean and predictable.

---

## 3. Spacing System
The layout uses the EndlessOS spacing scale:
- 4 / 8 / 12 / 16 / 20 / 24 / 32  

Rules:
- 16px vertical rhythm  
- 24–32px page padding  
- 20–24px section spacing  
- No custom spacing values  
- No fractional spacing  

Spacing is structural, not decorative.

---

## 4. Hierarchy & Grouping
Hierarchy is created through:
- Spacing  
- Typography  
- Card grouping  
- Section headers  

Hierarchy is **never** created through:
- Color  
- Borders  
- Shadows  
- Decorative elements  

Grouping must be clear, consistent, and predictable.

---

# Page Types

## 1. Hub Pages
Hub pages act as:
- High‑level discovery surfaces  
- Cross‑platform entry points  
- Content aggregators  

They use:
- Wide spacing  
- Large cards  
- Clear sectioning  
- Minimal density  

Hub pages must feel cinematic and inviting.

---

## 2. Platform Pages
Platform pages (Games, Tube, Music, Books, Events) inherit the global layout but apply:
- Platform accent  
- Platform background  
- Platform display typography  

Platform pages must feel distinct but structurally identical.

---

## 3. Utility Pages
Utility pages (Settings, Account, Legal, etc.) use:
- Higher density  
- Smaller cards  
- More text‑driven layouts  

Utility pages must remain calm and readable.

---

# Interaction Model

## Hover
Hover is allowed for:
- Tooltips  
- Subtle emphasis  
- Non‑essential clarity  

Hover must never:
- Reveal required information  
- Trigger layout changes  
- Animate aggressively  

## Keyboard & Focus
Focus must:
- Be predictable  
- Follow a logical order  
- Never trap the user  
- Never cause layout shift  

## Touch
Touch interactions must:
- Avoid hover‑dependent UI  
- Use large targets  
- Respect safe zones  

---

# Anti‑Patterns

The following violate the EndlessOS layout doctrine:

- Dynamic layout changes  
- Content‑driven resizing  
- Masonry grids  
- Overlapping elements  
- Edge‑to‑edge content  
- Inconsistent spacing  
- Platform‑specific layout hacks  
- Decorative layout elements  
- Layout shift during interaction  
- Overly dense pages  
- Overly sparse pages  
- Adaptive UI that changes based on content  
- Tooltips containing required information  

These are strictly prohibited.

---

# Summary

The EndlessOS layout design doctrine is deterministic, cinematic, and content‑first.  
It uses a stable grid, strict spacing, safe zones, and optional tooltips to create a modern, gaming‑grade layout system that scales cleanly across all surfaces and platforms.

All layout specifications inherit from this doctrine.
