# EndlessOS — Hub Behavior Specification

## Purpose
The Hub is the **world selector** of EndlessOS.  
It is not a navigation bar, not a home page, and not a dashboard.  
It is the **central switching surface** between Endless platforms:

- EndlessGames  
- EndlessMusic  
- EndlessTube  
- EndlessStream  
- EndlessRadio  
- EndlessBooks  
- EndlessEvents  
- EndlessMoments  
- EndlessRecaps  

The Hub provides:
- Platform discovery  
- Platform switching  
- A stable “reset point” for navigation  

The Hub must remain:
- Calm  
- Cinematic  
- Deterministic  
- Identity‑neutral  
- Free of utility clutter  

---

# Core Philosophy

## 1. The Hub Is a World Selector
The Hub is the **only place** where platform switching occurs.

Back never switches platforms.  
Utility pages never switch platforms.  
Modals never switch platforms.  
Platform pages never switch platforms.

Only the Hub can do this.

---

## 2. The Hub Is Not a Navigation Hub
The Hub is **not** used to navigate:

- Settings  
- Account  
- Wallet  
- Legal  
- Support  
- Profile  
- Utility pages  

Those belong to the **utility navigation system**, not the Hub.

The Hub is strictly for **platform selection**.

---

## 3. The Hub Is a Reset Point
The Hub acts as a “reset” for the user’s context.

If the user becomes deep in a navigation stack:
- Back unwinds the stack  
- Eventually returns to the Hub  
- The Hub resets the mental model  

The Hub is the **root** of the navigation tree.

---

## 4. The Hub Must Be Calm and Cinematic
The Hub is the most visually expressive surface in EndlessOS, but it must remain:

- Calm  
- Spacious  
- Cinematic  
- Identity‑neutral  
- Free of clutter  

It is the “world map,” not a dashboard.

---

# Hub Entry Points

The Hub can be accessed from:

### 1. The Profile Photo Radial Wheel  
The Hub icon appears in the wheel.

### 2. Back Button (Only When Hub Is Next in Stack)  
Back unwinds the stack until the Hub is reached.

### 3. Direct Navigation (Future: keyboard/controller)  
Optional future shortcuts.

The Hub must never be accessed by:
- Platform UI  
- Utility pages  
- Modals  
- Platform‑local settings  

---

# Hub Exit Points

Leaving the Hub always means:

**Selecting a platform tile.**

This pushes a new platform root page onto the navigation stack.

The Hub must never:
- Open utility pages  
- Open modals  
- Trigger system actions  
- Trigger platform‑local settings  

The Hub is strictly for platform entry.

---

# Hub Behavior Rules

## 1. The Hub Never Auto‑Hides
Unlike the top layer, the Hub is a **full‑screen surface**.

It must:
- Always remain visible  
- Never fade out  
- Never collapse  
- Never hide itself  

The Hub is a stable, persistent surface.

---

## 2. The Hub Has No Back Button
The Hub is the **root** of the navigation stack.

Back from the Hub:
- Does nothing  
- Leaves the user on the Hub  

The Hub cannot be “backed out of.”

---

## 3. The Hub Does Not Scroll Horizontally
The Hub uses:
- Vertical scroll only  
- Cinematic spacing  
- Large platform tiles  

Horizontal scroll is prohibited.

---

## 4. The Hub Does Not Use Platform Identity
The Hub must:
- Use neutral background  
- Use neutral typography  
- Use neutral iconography  

Platform identity is expressed **only** on platform pages.

---

## 5. The Hub Must Be Deterministic
The Hub must:
- Always load the same way  
- Always show the same platform order  
- Never reorder tiles dynamically  
- Never adapt based on usage  
- Never personalize layout  

Consistency is mandatory.

---

# Hub Interaction Behavior

## Hover
Hover may:
- Emphasize platform tiles  
- Show optional tooltips  

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
Touch must:
- Use large targets  
- Avoid hover‑dependent UI  
- Respect safe zones  

---

# Hub and Navigation Stack

The Hub is the **bottom** of the stack.

Example stack:

Hub
↓
Games
↓
Wallet
↓
Profile

Code

Back unwinds:

Profile → Wallet → Games → Hub

Code

Back never:
- Skips Games  
- Jumps directly to Hub  
- Switches platforms  

The Hub is simply the **root node**.

---

# Hub and Auto‑Hide Top Layer

The Hub is a **full‑screen surface**, but the top layer still behaves normally:

- The top layer appears on load  
- Auto‑hides after 10–20 seconds  
- Reappears when the user moves the mouse to the top  

The Hub itself never hides — only the top layer does.

---

# Hub and Radial Wheels

Radial wheels behave normally on the Hub:

- Profile wheel opens  
- Utility wheels open  
- Wheels do not affect Hub layout  
- Wheels do not shift tiles  

Back behavior:
- First closes any open wheel  
- Then does nothing (Hub is root)  

---

# Hub Anti‑Patterns

The Hub must never:
- Act as a dashboard  
- Display utility pages  
- Display account info  
- Display settings  
- Display notifications  
- Display platform‑local settings  
- Use accent colors  
- Use platform identity  
- Use dynamic tile ordering  
- Use hover‑dependent required info  
- Use aggressive animation  
- Use horizontal scroll  
- Use layout shift  

These violate the EndlessOS navigation doctrine.

---

# Summary

The Hub is the **world selector** of EndlessOS.  
It is the root of the navigation stack and the only place where platform switching occurs.

The Hub must remain:
- Calm  
- Cinematic  
- Deterministic  
- Identity‑neutral  
- Free of utility clutter  

It is the user’s anchor point — the stable center of the EndlessOS universe.