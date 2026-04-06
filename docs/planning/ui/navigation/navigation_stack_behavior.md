# EndlessOS — Navigation Stack Behavior Specification

## Purpose
The EndlessOS Navigation Stack defines how the system tracks page history, how Back unwinds that history, and how navigation flows between:

- The Hub  
- Platform pages  
- Utility pages  
- Modals  
- Radial wheels  
- System overlays  

The stack ensures navigation remains:
- Predictable  
- Deterministic  
- Console‑grade  
- Free of layout shift  
- Free of adaptive behavior  

This document defines the exact rules governing stack creation, mutation, and unwinding.

---

# Core Philosophy

## 1. The Stack Is Linear
EndlessOS uses a **strict, linear, push‑down stack**.

Every navigation action either:
- **Pushes** a new page onto the stack  
- **Pops** a page off the stack (Back)  
- **Clears** the stack (Hub button only)  

There is no branching, no graph traversal, no adaptive reordering.

---

## 2. The Stack Never Rewrites History
The stack must never:
- Replace entries  
- Reorder entries  
- Skip entries  
- Merge entries  
- Collapse entries  

Every page visited is a discrete entry.

---

## 3. The Stack Is Platform‑Scoped
The stack is scoped to the **current platform**.

Back never:
- Switches platforms  
- Jumps to the Hub unless it’s next in the stack  
- Teleports across platform boundaries  

Platform switching is **Hub‑only**.

---

# Stack Structure

The stack always begins with:

[Hub]

Example stack:

Hub
↓
Games
↓
Wallet
↓
Profile

Back unwinds:

Profile → Wallet → Games → Hub

---

# Stack Operations

## 1. Push
A new page is pushed onto the stack when:
- A platform tile is selected  
- A utility icon is selected  
- A utility wheel child icon is selected  
- A link inside a platform page is selected  
- A link inside a utility page is selected  

Push rules:
- Push always adds a new entry  
- Push never replaces the current entry  
- Push never clears the stack  

---

## 2. Pop (Back)
Back always pops **exactly one** entry.

Back never:
- Pops multiple entries  
- Skips entries  
- Jumps to Hub  
- Switches platforms  

Back is a pure stack pop.

---

## 3. Clear (Hub Button)
The Hub button is the **only** action that clears the stack.

Hub button behavior:
- Clears the entire stack  
- Pushes Hub as the only entry  
- Returns user to world selector  

This is the “reset” action.

---

# Stack Behavior by Context

## 1. Hub
The Hub is the root of the stack.

Back from Hub:
- Does nothing  

Hub cannot be popped.

---

## 2. Platform Pages
Platform pages push onto the stack.

Example:

Hub → Games → Game Details → Game Settings

Back unwinds:

Game Settings → Game Details → Games → Hub

Platform pages never:
- Replace stack entries  
- Collapse stack entries  
- Skip stack entries  

---

## 3. Utility Pages
Utility pages behave exactly like platform pages.

Example:

Games → Wallet → Profile → Legal

Back unwinds:

Legal → Profile → Wallet → Games

Utility pages never:
- Reset the stack  
- Jump to Hub  
- Switch platforms  

---

## 4. Modals
Modals do **not** enter the stack.

Modals are stack‑transparent.

Example:

Games → Wallet → Profile → [Edit Profile Modal]

Back sequence:

Modal closes → Profile → Wallet → Games → Hub

Modals never:
- Push onto the stack  
- Replace stack entries  
- Block stack pops  

---

## 5. Radial Wheels
Radial wheels are **not** part of the stack.

Back behavior:
- If a wheel is open → Back closes the wheel  
- If no wheel is open → Back pops the stack  

Wheels must never:
- Push onto the stack  
- Replace stack entries  
- Block stack pops  

---

## 6. Auto‑Hide Top Layer
The top layer does not affect the stack.

Stack behavior is identical whether the top layer is:
- Visible  
- Fading  
- Hidden  

Back always works.

---

# Stack Integrity Rules

## 1. No Duplicate Prevention
If the user navigates to the same page twice, the stack contains two entries.

Example:

Games → Wallet → Games → Wallet

This is allowed.

---

## 2. No Smart Collapsing
The stack must never:
- Collapse repeated entries  
- Remove redundant entries  
- Merge similar entries  

This preserves deterministic behavior.

---

## 3. No Adaptive Behavior
The stack must never adapt based on:
- User behavior  
- Time  
- Page type  
- Platform  
- Utility category  

The stack is static and predictable.

---

# Stack and Platform Switching

Platform switching is **Hub‑only**.

Example:

Games → Wallet → Profile

User presses Hub:

Stack clears → Hub

User selects Music:

Hub → Music

Back unwinds:

Music → Hub

Back never:
- Returns to Games  
- Returns to Wallet  
- Returns to Profile  

Platform stacks do not persist across switches.

---

# Stack and Deep Linking

Deep linking (future):
- Pushes the linked page onto the stack  
- Never replaces the stack  
- Never clears the stack  

Example:

Hub → Games → [Deep Link: Game Settings]

Stack becomes:

Hub → Games → Game Settings

---

# Anti‑Patterns

The navigation stack must never:
- Skip entries  
- Jump across entries  
- Collapse entries  
- Replace entries  
- Adapt based on context  
- Switch platforms  
- Jump to Hub  
- Behave differently per platform  
- Use dynamic stack logic  
- Use graph‑based navigation  
- Use breadcrumb logic  

These violate the EndlessOS navigation doctrine.

---

# Summary

The EndlessOS Navigation Stack is:
- Linear  
- Deterministic  
- Platform‑scoped  
- Hub‑rooted  
- Modal‑transparent  
- Wheel‑transparent  
- Console‑grade  

Back unwinds the stack one page at a time.  
Hub clears the stack.  
Platform switching is Hub‑only.  
Modals never enter the stack.  
Wheels never enter the stack.  

This ensures EndlessOS navigation remains predictable, calm, and future‑proof.