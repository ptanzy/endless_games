# EndlessOS — Page Lifecycle Specification

## Purpose
The Page Lifecycle defines how EndlessOS pages:
- Mount  
- Unmount  
- Load identity  
- Restore scroll  
- Trigger transitions  
- Interact with the navigation stack  
- Interact with the top layer  

This ensures deterministic, cinematic, platform‑consistent behavior.

---

# Core Philosophy

## 1. Pages Must Load Predictably
Every page must follow the same lifecycle sequence.  
No page may override or reorder lifecycle events.

---

## 2. Identity Loads Before Content
Platform identity (accent, background, typography) must load:
- Immediately after navigation  
- Before content  
- Before scroll restoration  
- Before transitions  

Identity must never flash or pop in.

---

## 3. Lifecycle Must Be Deterministic
Pages must:
- Mount the same way  
- Unmount the same way  
- Restore scroll the same way  
- Trigger transitions the same way  

No adaptive behavior.

---

# Lifecycle Sequence

## 1. Navigation Triggered
- Stack push/pop/clear occurs  
- Page instance is created  

## 2. Identity Activation
- Platform identity loads  
- Background loads  
- Typography rules apply  

## 3. Top Layer Reset
- Utility layer becomes visible  
- Auto‑hide timer resets  

## 4. Page Mount
- DOM mounts  
- Layout stabilizes  
- Safe zones applied  

## 5. Scroll Restoration
- If returning to a page → restore scroll  
- If new page → scroll to top  

## 6. Transition In
- 120–150ms fade  
- 2–4px micro‑shift  

## 7. Page Active
- User interacts normally  

---

# Unmount Sequence

## 1. Transition Out
- 120–150ms fade  
- No slide  
- No bounce  

## 2. Scroll Save
- Save scroll position (if returning later)  

## 3. Identity Deactivation (if exiting platform)
- Remove platform identity  
- Return to neutral state  

## 4. Page Destroy
- DOM unmounts  
- Memory cleanup  

---

# Scroll Rules

### New Page
- Scroll to top  

### Returning Page
- Restore previous scroll  

### Modal Close
- Do not change scroll  

### Wheel Close
- Do not change scroll  

### Hub Return
- Scroll resets  

---

# Interaction With Navigation

### Stack Push
- Full lifecycle runs  

### Stack Pop
- Unmount → mount sequence  

### Stack Clear (Hub)
- Identity resets  
- Scroll resets  
- Full lifecycle runs  

---

# Anti‑Patterns

Pages must never:
- Flash identity  
- Load content before identity  
- Animate layout  
- Shift content during mount  
- Restore scroll before layout  
- Use platform identity on Hub  
- Override lifecycle order  

---

# Summary

The Page Lifecycle ensures EndlessOS pages load, animate, and behave consistently across all platforms.  
Identity loads first, transitions are calm, scroll is deterministic, and navigation remains cinematic and predictable.
