# EndlessOS — Back Button Behavior Specification

## Purpose
The Back button is a **global navigation action** available through:
- The profile photo radial wheel  
- Keyboard shortcuts (future)  
- Controller input (future)  

Back is a **stack‑based navigation control**, not a platform switcher, not a hub shortcut, and not a teleport.

This specification defines exactly how Back behaves across:
- Platform pages  
- Utility pages  
- Modals  
- The Hub  
- The auto‑hide top layer  
- The radial wheel  

Back must always be:
- Predictable  
- Deterministic  
- Reversible  
- Linear  
- Console‑grade  

---

# Core Philosophy

## 1. Back Unwinds the Navigation Stack Linearly
Back always means:

**“Return to the previous screen in the navigation stack.”**

Back never:
- Jumps  
- Teleports  
- Skips  
- Reorders  
- Recomputes  
- Adapts based on context  

Back is **pure stack pop**.

---

## 2. Back Never Switches Platforms
Back does **not**:
- Move from Games → Music  
- Move from Tube → Books  
- Move from Events → Games  

Platform switching is **Hub‑only**.

Back only unwinds the stack **within the current platform context**.

---

## 3. Back Never Returns to the Hub (Unless It’s Next in the Stack)
The Hub is only reached by:
- Pressing the Hub button  
- Reaching the bottom of the stack naturally  

Back does **not**:
- Jump to the Hub  
- Treat the Hub as a special case  
- Skip intermediate pages  

The Hub is just another stack entry.

---

# Navigation Stack Model

EndlessOS uses a **strict, linear navigation stack**:

Hub
↓
Platform Page (Games)
↓
Utility Page (Wallet)
↓
Utility Page (Profile)
↓
Modal (Edit Profile)

Back unwinds:

Modal → Profile → Wallet → Games → Hub

Back never jumps from:
- Profile → Games  
- Wallet → Hub  
- Modal → Games  

Back always unwinds **one step at a time**.

---

# Back Behavior by Context

## 1. Platform Pages
Back from a platform page:
- Returns to the previous page in the stack  
- If the previous page is the Hub → return to Hub  
- If the stack is empty → do nothing  

Back never:
- Switches platforms  
- Returns to Hub unless it’s next in the stack  

---

## 2. Utility Pages
Utility pages behave exactly like platform pages.

Back from a utility page:
- Returns to the previous page (platform or utility)  
- Never jumps to Hub  
- Never jumps to platform root  

Example:

Games → Wallet → Profile

Back sequence:

Profile → Wallet → Games

---

## 3. Modals
Modals do **not** enter the navigation stack.

Back from a modal:
- Closes the modal  
- Returns to the underlying page  
- Does not pop the stack  

Example:

Games → Wallet → Profile → [Edit Profile Modal]

Back sequence:

Modal closes → Profile → Wallet → Games

Modals are **stack‑transparent**.

---

## 4. Hub
Back from the Hub:
- Does nothing  
- The Hub is the root of the stack  

Hub is the **stack origin**, not a page you can “back out of.”

---

# Interaction With Auto‑Hide Top Layer

## When the top layer is hidden:
- Back is still available through keyboard/controller  
- Back is still available through radial wheel (summon on hover)  

## When the top layer is visible:
- Back behaves normally  
- Back resets the auto‑hide timer  

## When a wheel is open:
- Back closes the wheel first  
- A second Back unwinds the stack  

This prevents accidental navigation.

---

# Interaction With Radial Wheels

Back interacts with wheels in a **two‑step model**:

### Step 1 — If a wheel is open  
Back closes the wheel.

### Step 2 — If no wheel is open  
Back unwinds the navigation stack.

This ensures:
- No accidental page navigation  
- Predictable behavior  
- Console‑grade consistency  

---

# Interaction With Platform Switching

Back never switches platforms.

If the user wants to switch platforms:
- They must go to the Hub  
- Then select a new platform  

Back only unwinds the current platform’s stack.

---

# Interaction With Utility Navigation

Utility navigation (top bar icons) **pushes** new entries onto the stack.

Example:

Games → Wallet → Profile

Back unwinds:

Profile → Wallet → Games

Utility navigation never:
- Replaces the current page  
- Resets the stack  
- Jumps to Hub  

---

# Edge Cases

## 1. Opening a modal from a modal
Not allowed.  
EndlessOS prohibits modal‑in‑modal stacking.

## 2. Opening a utility page from a modal
Not allowed.  
Modals must close before navigation.

## 3. Opening a platform page from a modal
Not allowed.  
Modals are local to the current page.

## 4. Back during a transition
Back is ignored until the transition completes.

---

# Anti‑Patterns

Back must never:
- Jump across the stack  
- Skip pages  
- Teleport to Hub  
- Switch platforms  
- Close the top layer  
- Trigger layout shift  
- Animate aggressively  
- Behave differently per platform  

These violate the EndlessOS navigation doctrine.

---

# Summary

The Back button is a **pure stack‑pop navigation action**.

It must always:
- Unwind the stack linearly  
- Respect modal transparency  
- Never switch platforms  
- Never jump to Hub  
- Never shift layout  
- Behave identically across all platforms  

This ensures EndlessOS navigation remains:
- Predictable  
- Console‑grade  
- Deterministic  
- Calm  
- Scalable  
- Future‑proof  