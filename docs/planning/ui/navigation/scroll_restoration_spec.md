# EndlessOS — Scroll Restoration Specification

## Purpose
Scroll Restoration defines how EndlessOS manages scroll position when:
- Navigating between pages  
- Opening/closing modals  
- Opening/closing wheels  
- Returning to previous pages  
- Switching platforms  
- Returning to Hub  

Scroll behavior must remain:
- Deterministic  
- Predictable  
- Cinematic  
- Non‑adaptive  
- Free of layout shift  

This document defines the rules for scroll restoration across the OS.

---

# Core Philosophy

## 1. Scroll Must Always Be Predictable
Users must always know:
- When scroll resets  
- When scroll restores  
- When scroll is preserved  

No surprises.

---

## 2. Scroll Must Never Shift Layout
Scroll restoration must:
- Occur after layout stabilizes  
- Never cause reflow  
- Never cause content jumps  
- Never animate scroll  

---

## 3. Scroll Behavior Must Be Deterministic
Scroll rules must:
- Never adapt based on context  
- Never vary by platform  
- Never vary by page type  

---

# Scroll Rules

## 1. New Page
When navigating to a new page:
- Scroll resets to **top**  
- No animation  

This applies to:
- Platform entry  
- Utility entry  
- Platform sub‑pages  

---

## 2. Returning to a Page
When navigating back:
- Restore previous scroll position  
- After layout stabilizes  
- Without animation  

This ensures:
- No jarring jumps  
- No partial loads  

---

## 3. Modal Behavior

### Opening a Modal
- Scroll position is preserved  
- Page behind modal does not move  

### Closing a Modal
- Scroll position remains unchanged  
- No restoration needed  

Modals must never affect scroll.

---

## 4. Wheel Behavior

### Opening a Wheel
- Scroll position is preserved  

### Closing a Wheel
- Scroll position remains unchanged  

Wheels must never affect scroll.

---

## 5. Hub Behavior

### Navigating to Hub
- Scroll resets to top  

### Navigating from Hub
- Scroll resets to top  

Hub is always a fresh state.

---

## 6. Platform Switching
Platform switching is Hub‑only.

Sequence:
1. Return to Hub → scroll resets  
2. Enter new platform → scroll resets  

No scroll restoration across platforms.

---

# Scroll Save Rules

Scroll is saved:
- On page exit  
- On stack pop  
- On modal open  
- On wheel open  

Scroll is cleared:
- On stack clear  
- On platform exit  
- On Hub return  

---

# Timing Rules

Scroll restoration occurs:
- After identity loads  
- After layout stabilizes  
- Before transition in  

Never during animation.

---

# Anti‑Patterns

Scroll must never:
- Animate  
- Ease  
- Snap  
- Jump mid‑transition  
- Restore before layout  
- Restore after transition  
- Persist across platforms  
- Persist across Hub  

These violate the EndlessOS navigation doctrine.

---

# Summary

Scroll Restoration in EndlessOS is:
- Deterministic  
- Predictable  
- Cinematic  
- Non‑adaptive  
- Identity‑neutral  

New pages reset scroll.  
Returning pages restore scroll.  
Modals and wheels never affect scroll.  
Hub always resets scroll.  
Platform switching never preserves scroll.
