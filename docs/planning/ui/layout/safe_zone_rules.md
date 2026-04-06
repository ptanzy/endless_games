# EndlessOS — Safe Zone Rules

## Purpose
Safe zones define the non‑negotiable boundaries that protect readability, usability, and layout stability across EndlessOS.  
They ensure that no content, tooltip, navigation element, or interactive component ever collides with screen edges or becomes unreadable.

Safe zones are a structural guarantee and apply to:
- All page types  
- All platforms (Games, Tube, Music, Books, Events)  
- All layouts (hub, platform, utility)  
- All interaction layers (hover, focus, touch)  
- All tooltip placements  

Safe zones inherit from:
- layout_design_doctrine.md  
- layout_system_overview.md  

---

# Core Principles

## 1. Safe Zones Are Sacred
Safe zones:
- Cannot be overridden  
- Cannot be reduced  
- Cannot be platform‑specific  
- Cannot collapse dynamically  
- Cannot be bypassed by tooltips or popovers  

They are a **system‑level constraint**, not a design suggestion.

---

## 2. No Content May Touch Screen Edges
All content must remain inside the safe zone boundary.

This includes:
- Text  
- Cards  
- Buttons  
- Icons  
- Tooltips  
- Dropdowns  
- Modals  
- Navigation elements  

Nothing may break the boundary.

---

## 3. Safe Zones Scale by Breakpoint
Safe zones adjust proportionally with screen size.

### Large Screens (≥1280px)
- **Horizontal safe zone:** 64px  
- **Vertical safe zone:** 48px  

### Medium Screens (768–1279px)
- **Horizontal safe zone:** 48px  
- **Vertical safe zone:** 32px  

### Small Screens (<768px)
- **Horizontal safe zone:** 24px  
- **Vertical safe zone:** 24px  

Rules:
- No fractional values  
- No custom overrides  
- No platform‑specific adjustments  

---

# Safe Zone Application

## 1. Page Frame
The global page frame must always sit inside the safe zone.

This includes:
- Page title  
- Section headers  
- Content grids  
- Horizontal rows  
- Filters/sorting  
- Featured hero  

Nothing may extend beyond the boundary.

---

## 2. Tooltips
Tooltips must:
- Always appear **inside** the safe zone  
- Reposition automatically to avoid clipping  
- Never overlap the cursor  
- Never cover critical UI  
- Never force layout shift  

Tooltip placement priority:
1. Above  
2. Below  
3. Left  
4. Right  

If all four positions violate safe zones, the tooltip must:
- Reduce width (min 160px)  
- Reduce padding (min 6px)  
- Never overflow  

---

## 3. Dropdowns & Popovers
Dropdowns must:
- Open inward (toward the center of the screen)  
- Never overflow the safe zone  
- Reposition automatically if needed  
- Never resize content to fit  

Popovers must:
- Respect safe zones  
- Never animate aggressively  
- Never shift layout  

---

## 4. Navigation
Navigation elements must:
- Sit fully inside the safe zone  
- Never collide with edges  
- Never shrink to fit  
- Never overlap content  

Platform identity bars must also respect safe zones.

---

## 5. Cards & Grids
Cards must:
- Maintain spacing inside safe zones  
- Never touch screen edges  
- Never resize dynamically  
- Never break grid alignment  

Grid padding must always be:
- 24px minimum (inside safe zone)  
- 24px between cards  

---

## 6. Modals
Modals must:
- Be centered  
- Respect safe zones on all sides  
- Never exceed 80% of viewport width  
- Never exceed 80% of viewport height  

Modal content must scroll internally, not the page.

---

# Interaction Rules

## Hover
Hover elements must:
- Never extend beyond safe zones  
- Never cause layout shift  
- Never reveal required information  

## Focus
Focus rings must:
- Stay inside safe zones  
- Never clip  
- Never cause reflow  

## Touch
Touch targets must:
- Remain inside safe zones  
- Maintain 44px minimum size  
- Avoid edge collisions  

---

# Anti‑Patterns

The following violate safe zone rules:

- Edge‑to‑edge content  
- Cards touching screen edges  
- Tooltips overflowing the viewport  
- Dropdowns clipped by edges  
- Modals exceeding safe zone boundaries  
- Platform identity bars touching edges  
- Dynamic resizing to “fit” content  
- Hover elements that escape safe zones  
- Layout shift caused by repositioning  

These are strictly prohibited.

---

# Summary

Safe zones are the structural backbone of EndlessOS.  
They ensure clarity, readability, and predictability across all layouts, platforms, and interaction modes.

Safe zones:
- Are fixed  
- Are non‑negotiable  
- Apply to all components  
- Protect against layout shift  
- Ensure cinematic, console‑grade presentation  

All layout specifications must comply with these rules.
