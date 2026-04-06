# EndlessOS — Navigation System Specification

## Purpose
The EndlessOS Navigation System defines how users move between:
- The Hub  
- Platform pages  
- Utility pages  
- Modals  
- Radial wheels  
- System overlays  
- The auto‑hide top layer  

This system ensures navigation remains:
- Predictable  
- Deterministic  
- Console‑grade  
- Calm and cinematic  
- Free of layout shift  
- Free of adaptive behavior  
- Scalable for future platforms and utilities  

This is the top‑level doctrine that governs all navigation behavior across EndlessOS.

---

# Core Principles

## 1. Navigation Is Stack‑Based
EndlessOS uses a **strict, linear navigation stack**.

Every navigation action either:
- Pushes a new page  
- Pops a page (Back)  
- Clears the stack (Hub button only)  

There is no graph traversal, no adaptive routing, no dynamic reordering.

---

## 2. The Hub Is the Root of All Navigation
The Hub is:
- The world selector  
- The root of the navigation stack  
- The only place where platform switching occurs  

Back never switches platforms.  
Utility pages never switch platforms.  
Modals never switch platforms.

Only the Hub can do this.

---

## 3. Back Is a Pure Stack Pop
Back always means:

**“Return to the previous page in the navigation stack.”**

Back never:
- Skips pages  
- Jumps to Hub  
- Switches platforms  
- Rewrites history  

Back unwinds the stack one entry at a time.

---

## 4. Modals Are Stack‑Transparent
Modals:
- Do not enter the stack  
- Do not replace stack entries  
- Do not block stack pops  

Back closes modals first, then unwinds the stack.

---

## 5. Radial Wheels Are Not Navigation
Radial wheels:
- Do not enter the stack  
- Do not replace stack entries  
- Do not block stack pops  

Back closes wheels first, then unwinds the stack.

---

## 6. The Top Layer Is Summonable, Not Persistent
The top layer:
- Appears on load  
- Auto‑hides after 10–20 seconds  
- Reappears when the user moves the mouse to the top  

Navigation works identically whether the top layer is visible or hidden.

---

## 7. Navigation Must Never Shift Layout
Navigation must:
- Never push content  
- Never resize content  
- Never cause reflow  
- Never animate aggressively  

All transitions occur **above** the layout.

---

# Navigation Surfaces

The EndlessOS Navigation System includes:

1. **Hub**  
2. **Platform Pages**  
3. **Utility Pages**  
4. **Modals**  
5. **Radial Wheels**  
6. **Auto‑Hide Top Layer**  
7. **System Overlays**  

Each surface has strict rules.

---

# 1. Hub Navigation

The Hub:
- Is the root of the stack  
- Is the only platform switcher  
- Never hides  
- Never scrolls horizontally  
- Never shows utility content  

Selecting a platform tile:
- Pushes the platform root page onto the stack  

Back from Hub:
- Does nothing  

Hub button:
- Clears the stack  
- Returns to Hub  

---

# 2. Platform Navigation

Platform pages:
- Push onto the stack  
- Never replace entries  
- Never collapse entries  
- Never skip entries  

Back unwinds platform pages in reverse order.

Platform pages never:
- Switch platforms  
- Jump to Hub  
- Open utility pages automatically  

---

# 3. Utility Navigation

Utility pages:
- Push onto the stack  
- Behave exactly like platform pages  
- Never reset the stack  
- Never switch platforms  

Utility navigation is accessed through:
- Utility bar icons  
- Utility wheel icons  
- Profile wheel  

Utility pages never:
- Replace platform pages  
- Collapse stack entries  
- Jump to Hub  

---

# 4. Modal Navigation

Modals:
- Do not enter the stack  
- Do not replace stack entries  
- Do not block stack pops  

Back behavior:
1. If a modal is open → close modal  
2. Else → pop stack  

Modals must close before navigation occurs.

---

# 5. Radial Wheel Navigation

Radial wheels:
- Are not part of the stack  
- Are not pages  
- Are not navigation states  

Back behavior:
1. If a wheel is open → close wheel  
2. Else → pop stack  

Wheels must never:
- Push onto the stack  
- Replace stack entries  
- Block stack pops  

---

# 6. Auto‑Hide Top Layer Navigation

The top layer:
- Does not affect the stack  
- Does not block navigation  
- Does not change Back behavior  

When hidden:
- Moving the mouse to the top summons it  
- Navigation remains fully functional  

---

# 7. System Overlay Navigation

System overlays (e.g., update required):
- Sit above all surfaces  
- Block interaction with underlying pages  
- Must be dismissed before navigation continues  

Overlays do not enter the stack.

---

# Navigation Flow Examples

## Example 1 — Simple Flow
Hub → Games → Wallet → Profile

Back:
Profile → Wallet → Games → Hub

---

## Example 2 — Utility Navigation
Games → Wallet → Legal → Privacy

Back:
Privacy → Legal → Wallet → Games → Hub

---

## Example 3 — Modals
Games → Wallet → Profile → [Edit Profile Modal]

Back:
Modal closes → Profile → Wallet → Games → Hub

---

## Example 4 — Radial Wheels
Games → Wallet → [Profile Wheel Open]

Back:
Wheel closes → Wallet → Games → Hub

---

## Example 5 — Platform Switching
Games → Wallet → Profile

User presses Hub:
Stack clears → Hub

User selects Music:
Hub → Music

Back:
Music → Hub

---

# Anti‑Patterns

The navigation system must never:
- Skip stack entries  
- Jump across entries  
- Collapse entries  
- Replace entries  
- Adapt based on context  
- Switch platforms automatically  
- Jump to Hub unexpectedly  
- Use breadcrumb logic  
- Use graph‑based navigation  
- Use dynamic routing  
- Use layout‑shifting transitions  

These violate the EndlessOS navigation doctrine.

---

# Summary

The EndlessOS Navigation System is:
- Linear  
- Deterministic  
- Hub‑rooted  
- Platform‑scoped  
- Modal‑transparent  
- Wheel‑transparent  
- Console‑grade  

Back unwinds the stack one page at a time.  
Hub clears the stack.  
Platform switching is Hub‑only.  
Modals and wheels never enter the stack.  
The top layer auto‑hides without affecting navigation.  

This system ensures EndlessOS navigation remains predictable, calm, and future‑proof.