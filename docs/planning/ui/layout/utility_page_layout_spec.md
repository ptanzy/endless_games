# EndlessOS — Utility Page Layout Specification

## Purpose
Utility pages provide access to system‑level and account‑level functions such as:
- Settings  
- Account  
- Legal  
- Support  
- Storage  
- Updates  
- Privacy  
- Membership  
- Wallet  

These pages are **text‑driven**, **higher‑density**, and **function‑oriented**, but must still follow the EndlessOS doctrines of:
- Deterministic layout  
- Calm, cinematic presentation  
- Neutral visual language  
- Strict safe zone compliance  
- Zero layout shift  
- Optional, non‑essential tooltips  

It inherits from:
- layout_design_doctrine.md  
- layout_system_overview.md  
- safe_zone_rules.md  
- tooltip_spec.md  
- visual_language_design.md  

---

# Core Philosophy

Utility pages must be:
- **Functional** (clarity over aesthetics)  
- **Calm** (no visual noise)  
- **Deterministic** (no dynamic resizing or adaptive layout)  
- **Neutral** (no accent colors, no platform identity)  
- **Readable** (text‑first, structured, scannable)  

Utility pages are **not** platform pages.  
They do **not** use platform accents or backgrounds.  
They use the **global neutral theme**.

---

# Page Structure

Utility pages follow a strict, predictable structure:

┌──────────────────────────────────────────────┐
│ Global Header (Platform or System)           │
├──────────────────────────────────────────────┤
│ Safe Zone                                     │
│  ┌────────────────────────────────────────┐   │
│  │ Page Title + Optional Metadata         │   │
│  ├────────────────────────────────────────┤   │
│  │ Optional Sub‑Navigation                │   │
│  ├────────────────────────────────────────┤   │
│  │ Section Blocks (Cards or Lists)        │   │
│  ├────────────────────────────────────────┤   │
│  │ Optional Footer Notes                  │   │
│  └────────────────────────────────────────┘   │
└──────────────────────────────────────────────┘

Code

---

# 1. Page Title Row

The title row includes:
- Page title (e.g., “Settings”, “Account”, “Legal”)  
- Optional metadata (e.g., “Last updated 2 days ago”)  

Spacing:
- 24px top padding  
- 16px bottom padding  
- 24px horizontal padding  

Typography:
- Inter 28–32px, weight 600  
- Neutral color only  

Rules:
- No accent colors  
- No platform identity  
- No animations  

---

# 2. Optional Sub‑Navigation

Some utility pages may require sub‑navigation, such as:
- Settings categories  
- Account tabs  
- Legal sections  

Sub‑navigation must:
- Use neutral styling  
- Use pill or tab components  
- Never use accent colors  
- Never animate aggressively  
- Never shift layout  

Spacing:
- 16px above  
- 16px below  

---

# 3. Section Blocks

Utility pages are composed of **stacked section blocks**, each containing:
- A section header  
- A content block (card, list, or form)  

### Section Header
- Inter 18px weight 600  
- Neutral color  
- 20px top padding  
- 12px bottom padding  
- 24px horizontal padding  

### Section Types
- **Card Sections** (Settings, Account, Support)  
- **List Sections** (Legal, Privacy, Licenses)  
- **Form Sections** (Profile, Preferences)  

Rules:
- No dynamic resizing  
- No collapsible sections unless explicitly defined  
- No masonry layouts  
- No decorative elements  

---

# 4. Card Layout

Utility cards must be:
- Neutral  
- Text‑first  
- High‑readability  
- Non‑interactive except for buttons or toggles  

Card spacing:
- 16px vertical spacing  
- 24px horizontal padding  
- 16px internal padding  

Card content may include:
- Title  
- Description  
- Toggle  
- Button  
- Link  
- Metadata  

Cards must never:
- Use accent colors  
- Animate on hover  
- Resize dynamically  
- Shift layout  

---

# 5. List Layout

Used for:
- Legal documents  
- Privacy policies  
- Licenses  
- Terms  

List rules:
- Left‑aligned  
- Neutral typography  
- 16px vertical spacing  
- 24px horizontal padding  
- No bullets unless necessary  
- No decorative icons  

---

# 6. Form Layout

Used for:
- Profile settings  
- Preferences  
- Account details  

Form rules:
- 24px section spacing  
- 16px field spacing  
- 24px horizontal padding  
- Neutral input fields  
- Neutral labels  
- Neutral borders  

Forms must never:
- Animate  
- Resize dynamically  
- Shift layout  

---

# 7. Interaction Behavior

## Hover
Hover may:
- Show tooltips  
- Emphasize buttons subtly  

Hover must not:
- Reveal required information  
- Shift layout  
- Animate aggressively  

## Focus
Focus must:
- Follow predictable order  
- Never trap the user  
- Never cause reflow  

## Touch
Touch interactions must:
- Avoid hover‑dependent UI  
- Use large targets  
- Respect safe zones  

---

# 8. Tooltip Usage

Tooltips on utility pages:
- Are optional  
- Appear on hover or focus  
- Must never contain required information  
- Must never shift layout  
- Must use subtle fade (120–150ms)  
- Must respect safe zones  

Valid tooltip content:
- Descriptions  
- Clarifications  
- Metadata  

Invalid tooltip content:
- Required instructions  
- Required labels  
- Buttons or interactive elements  

---

# 9. Loading States

Utility pages use:
- Neutral skeleton loaders  
- No shimmer animations >150ms  
- No parallax  
- No bouncing placeholders  
- No layout shift  

Skeletons must:
- Match card or list shape  
- Respect spacing  
- Respect safe zones  

---

# 10. Empty States

Empty states must:
- Be centered  
- Use neutral illustration or icon  
- Use neutral text  
- Never use accent colors  
- Never animate aggressively  

Empty states must not:
- Use humor  
- Use personality  
- Use decorative graphics  

---

# 11. Error States

Error states must:
- Use semantic red  
- Provide a retry button  
- Never use accent colors  
- Never animate aggressively  

Error messages must be:
- Clear  
- Neutral  
- Non‑technical  

---

# Anti‑Patterns

Utility pages must never include:
- Accent‑colored UI elements  
- Platform identity colors  
- Masonry layouts  
- Dynamic resizing  
- Content‑driven layout changes  
- Animated section headers  
- Hover‑dependent required information  
- Parallax scrolling  
- Autoplaying media  
- Layout shift during interaction  
- Overly dense pages  
- Overly sparse pages  
- Platform‑specific layout hacks  

These violate the EndlessOS layout doctrine.

---

# Summary

Utility pages are functional, text‑driven surfaces that must remain calm, neutral, and deterministic.  
They use structured sections, predictable spacing, and optional tooltips to maintain clarity and readability.

This specification ensures:
- Consistent structure  
- High readability  
- Safe zone compliance  
- Neutral visual language  
- Zero layout shift  
- Cinematic calmness  