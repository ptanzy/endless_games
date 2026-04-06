# EndlessOS — Utility Modals Specification

## Purpose
Utility modals provide **quick, lightweight, system‑level interactions** that do not require navigating to a full utility page.  
They are accessed from:
- The utility navigation bar  
- The profile photo radial wheel  
- Multi‑utility wheel icons  
- Contextual system actions  

Utility modals are:
- Faster than utility pages  
- More lightweight than global modals  
- More general than platform‑local modals  

They are the “micro‑tools” of EndlessOS.

Utility modals inherit from:
- global_modal_system_planning.md  
- layout_design_doctrine.md  
- visual_language_design.md  
- safe_zone_rules.md  
- tooltip_spec.md  
- utility_navigation_spec.md  

---

# Core Philosophy

## 1. Utility Modals Are System‑Level
Utility modals:
- Apply across the entire OS  
- Are not tied to any platform  
- Must never use platform identity  
- Must never use accent colors  
- Must never use platform backgrounds  

They are **global**, not contextual.

---

## 2. Lightweight and Fast
Utility modals must:
- Open instantly  
- Close instantly  
- Contain minimal content  
- Require minimal interaction  
- Avoid multi‑step flows  

They are designed for **quick actions**, not deep configuration.

---

## 3. Deterministic and Non‑Adaptive
Utility modals must:
- Always appear centered  
- Always use the same size rules  
- Never resize dynamically  
- Never shift layout  
- Never adapt based on content  

Consistency is mandatory.

---

## 4. Neutral Visual Language
Utility modals must:
- Use neutral backgrounds  
- Use neutral borders  
- Use neutral icons  
- Use neutral typography  

They must never:
- Use accent colors  
- Use platform colors  
- Use semantic colors except for errors  

---

# Modal Structure

Utility modals follow a compact, consistent structure:

┌──────────────────────────────────────────────┐
│ Overlay (neutral, 60–70% opacity)            │
│   ┌──────────────────────────────────────┐    │
│   │ Utility Modal Container              │    │
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

# Size Rules

Utility modals must be compact:

- **Width:** 320–420px  
- **Max height:** 60–70% of viewport  
- **Internal padding:** 24px  
- **Element spacing:** 16px  

If content exceeds height:
- The modal scrolls internally  
- The page behind does not scroll  

---

# Trigger Rules

Utility modals may be triggered by:
- Utility bar icons  
- Radial wheel child icons  
- Profile photo wheel  
- System actions (e.g., “Sign out”)  

Triggers must:
- Use neutral icons  
- Never use accent colors  
- Never animate aggressively  

---

# Content Types

Utility modals support the following content types:

### 1. Quick Settings
- Dark mode toggle  
- Autoplay toggle  
- Notifications toggle  
- Language selector  

### 2. Account Actions
- Sign out  
- Switch account  
- View membership status  
- Quick wallet balance  

### 3. System Actions
- Clear cache  
- Restart required  
- Update available  
- Storage warning  

### 4. Micro‑Forms
- Rename device  
- Change email  
- Change password (step 1 only)  

### 5. Information Panels
- Membership tier summary  
- Rewards summary  
- Legal notice preview  

Utility modals must never contain:
- Multi‑step flows  
- Long forms  
- Platform‑specific settings  

---

# Interaction Behavior

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

# Motion Rules

Utility modals use the same motion rules as global modals:

Allowed:
- 120–150ms opacity fade  
- 2–4px micro‑shift  

Prohibited:
- Bounce  
- Elastic  
- Slide  
- Parallax  
- Scale  
- Rotation  

Motion must support clarity, not personality.

---

# Safe Zone Compliance

Utility modals must:
- Sit fully inside safe zones  
- Never touch screen edges  
- Never exceed 420px width  
- Never exceed 70% viewport height  

If a modal would violate safe zones:
- Reduce width  
- Reduce height  
- Never overflow  

---

# Button Rules

Buttons must:
- Use neutral colors  
- Use semantic colors only for destructive actions  
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

# Tooltip Usage

Tooltips in utility modals:
- Are optional  
- Appear on hover or focus  
- Must never contain required information  
- Must never shift layout  
- Must respect safe zones  

Valid tooltip content:
- Clarifications  
- Descriptions  
- Metadata  

Invalid tooltip content:
- Required instructions  
- Buttons  
- Interactive elements  

---

# Example Utility Modals

### Account
- “Sign Out” confirmation  
- “Membership Status” quick view  
- “Wallet Balance” quick view  

### System
- “Update Available”  
- “Restart Required”  
- “Clear Cache”  

### Settings
- “Dark Mode” toggle  
- “Language” selector  
- “Notifications” toggle  

### Support
- “Contact Support” quick form  
- “Report Issue” micro‑form  

---

# Anti‑Patterns

Utility modals must never include:
- Accent‑colored UI elements  
- Platform‑colored backgrounds  
- Dynamic resizing  
- Layout shift  
- Hover‑dependent required information  
- Parallax  
- Autoplaying media  
- Full‑screen modal behavior  
- Multi‑step flows  
- Platform‑specific settings  

These violate the EndlessOS modal doctrine.

---

# Summary

Utility modals provide fast, lightweight, system‑level interactions without requiring full page navigation.  
They must remain:
- Compact  
- Neutral  
- Deterministic  
- Calm  
- Safe‑zone compliant  
- Consistent across the OS  

They are the micro‑tools of EndlessOS, enabling quick actions while preserving the platform’s cinematic, consol