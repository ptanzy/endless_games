# EndlessOS — Global Modal System Planning

## Purpose
The Global Modal System defines how all modal surfaces behave across EndlessOS.  
Modals are system‑level UI primitives used for:
- Confirmations  
- Warnings  
- Errors  
- Settings overlays  
- Account actions  
- Utility interactions  
- Multi‑step flows  

This planning document ensures modals remain:
- Calm  
- Deterministic  
- Neutral  
- Cinematic  
- Non‑intrusive  
- Safe‑zone compliant  

All modals inherit from:
- layout_design_doctrine.md  
- visual_language_design.md  
- safe_zone_rules.md  
- tooltip_spec.md  
- utility_page_layout_spec.md  

---

# Core Philosophy

## 1. Modals Are System‑Level, Not Platform‑Level
Modals must never express platform identity.

They must:
- Use neutral colors  
- Use neutral backgrounds  
- Use neutral borders  
- Use neutral typography  

Modals must never:
- Use accent colors  
- Use platform backgrounds  
- Use platform typography  

Modals belong to the **system**, not the platform.

---

## 2. Modals Must Never Shift Layout
Modals appear **above** the layout, not within it.

This means:
- No reflow  
- No content push  
- No resizing of underlying elements  
- No dynamic repositioning  

The page beneath must remain perfectly still.

---

## 3. Modals Must Be Calm and Cinematic
Motion must be:
- Subtle  
- Slow  
- Neutral  
- Predictable  

Allowed:
- 120–150ms opacity fade  
- 2–4px micro‑shift  

Prohibited:
- Bounce  
- Elastic  
- Slide  
- Parallax  
- Scale‑up  
- Rotation  

Modals must never draw attention to themselves.

---

## 4. Modals Must Respect Safe Zones
Modals must:
- Sit fully inside safe zones  
- Never touch screen edges  
- Never exceed 80% of viewport width  
- Never exceed 80% of viewport height  

If content exceeds modal height:
- The modal scrolls internally  
- The page behind does not scroll  

---

## 5. Modals Must Be Deterministic
Modals must:
- Always appear centered  
- Always use the same size rules  
- Always use the same motion rules  
- Always use the same spacing rules  

No adaptive sizing.  
No content‑driven resizing.  
No dynamic width changes.

---

# Modal Types

EndlessOS supports **four** modal types:

1. **Standard Modal**  
2. **Confirmation Modal**  
3. **Critical Modal**  
4. **Utility Modal**  

Each type has strict rules.

---

## 1. Standard Modal
Used for:
- Settings overlays  
- Forms  
- Multi‑step flows  
- Information dialogs  

Size:
- 480–640px width  
- 80% max height  

Content:
- Title  
- Description  
- Body content  
- Buttons  

Buttons:
- Neutral primary  
- Neutral secondary  
- No accent colors  

---

## 2. Confirmation Modal
Used for:
- “Are you sure?” actions  
- Reversible operations  

Size:
- 400–520px width  

Content:
- Title  
- Short description  
- Primary + secondary buttons  

Primary button:
- Neutral  
- Never accent  

---

## 3. Critical Modal
Used for:
- Irreversible actions  
- Deletions  
- Security warnings  

Size:
- 400–520px width  

Content:
- Title  
- Short description  
- Semantic red icon (optional)  
- Primary + secondary buttons  

Primary button:
- Semantic red  
- Never accent  

---

## 4. Utility Modal
Used for:
- Quick actions  
- Micro‑settings  
- Small forms  
- Account actions  

Size:
- 320–420px width  

Content:
- Title  
- Body  
- Buttons  

Utility modals must be:
- Compact  
- Fast  
- Minimal  

---

# Modal Structure

All modals follow the same structure:

┌──────────────────────────────────────────────┐
│ Overlay (neutral, 60–70% opacity)            │
│   ┌──────────────────────────────────────┐    │
│   │ Modal Container                      │    │
│   │  ┌────────────────────────────────┐  │    │
│   │  │ Title Row                      │  │    │
│   │  ├────────────────────────────────┤  │    │
│   │  │ Body Content                   │  │    │
│   │  ├────────────────────────────────┤  │    │
│   │  │ Button Row                     │  │    │
│   │  └────────────────────────────────┘  │    │
│   └──────────────────────────────────────┘    │
└──────────────────────────────────────────────┘

---

# Interaction Rules

## Hover
Hover may:
- Emphasize buttons  
- Show tooltips  

Hover must not:
- Reveal required information  
- Shift layout  

## Focus
Focus must:
- Follow predictable order  
- Never trap the user  
- Never cause reflow  

## Touch
Touch must:
- Use large targets  
- Avoid hover‑dependent UI  
- Respect safe zones  

---

# Overlay Behavior

The overlay:
- Uses neutral black at 60–70% opacity  
- Fades in over 120–150ms  
- Must not blur the background  
- Must not animate aggressively  

The overlay must:
- Block interaction with the page  
- Not shift layout  
- Not scroll  

---

# Button Rules

Buttons must:
- Use neutral colors  
- Use semantic colors only for critical actions  
- Never use accent colors  
- Never use platform colors  

Button order:
- Primary on the right  
- Secondary on the left  

Spacing:
- 16px between buttons  
- 24px top padding  
- 24px bottom padding  

---

# Motion Rules

Modal motion must:
- Fade in (120–150ms)  
- Micro‑shift upward (2–4px)  
- Never bounce  
- Never scale  
- Never rotate  
- Never slide  

Motion must support clarity, not personality.

---

# Accessibility Rules

Modals must:
- Trap focus inside the modal  
- Close on ESC  
- Close on overlay click (unless critical)  
- Provide clear labels  
- Provide clear descriptions  
- Never rely on hover for required info  

Screen readers must:
- Announce modal title  
- Announce modal role  
- Announce button labels  

---

# Anti‑Patterns

The following violate the modal system:

- Accent‑colored buttons  
- Platform‑colored modals  
- Dynamic resizing  
- Layout shift  
- Slide‑in animations  
- Bounce animations  
- Parallax  
- Full‑screen modals  
- Edge‑to‑edge modals  
- Hover‑dependent required information  
- Modals that scroll the page behind  
- Modals that exceed safe zones  

These are strictly prohibited.

---

# Summary

The Global Modal System ensures all modals across EndlessOS remain:
- Calm  
- Neutral  
- Deterministic  
- Cinematic  
- Safe‑zone compliant  
- Consistent across all platforms  

Modals are system‑level primitives that must never express platform identity or violate the EndlessOS visual language.

This planning document defines the foundation for all modal behavior across the OS.