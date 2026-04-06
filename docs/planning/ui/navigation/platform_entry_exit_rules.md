# platform_entry_exit_rules
# EndlessOS — Platform Entry & Exit Specification

## Purpose
Platform entry and exit define how users transition between:
- The Hub (world selector)
- Platform root pages (Games, Music, Tube, Books, Events, etc.)
- Platform sub‑pages
- Utility pages
- System surfaces

This spec ensures platform transitions remain:
- Cinematic  
- Deterministic  
- Identity‑consistent  
- Stack‑correct  
- Free of layout shift  
- Free of adaptive behavior  

Platform entry and exit are foundational to the EndlessOS navigation model.

---

# Core Philosophy

## 1. Platforms Are Worlds
Each platform is a **self‑contained world** with:
- Its own identity  
- Its own accent color  
- Its own background  
- Its own content structure  

Entering a platform is entering a world.  
Exiting a platform is leaving that world.

---

## 2. Platform Entry Is Intentional
Platform entry must:
- Always be user‑initiated  
- Always be explicit  
- Never be automatic  
- Never be triggered by utility actions  
- Never be triggered by modals  

Only the Hub can initiate platform entry.

---

## 3. Platform Exit Is Controlled
Platform exit must:
- Always return to the Hub  
- Never jump to another platform  
- Never skip the Hub  
- Never be triggered by Back unless Hub is next in stack  

Platform switching is **Hub‑only**.

---

# Platform Entry

Platform entry occurs when the user selects a platform tile on the Hub.

## Entry Sequence
1. User selects a platform tile  
2. Platform root page is **pushed** onto the navigation stack  
3. Platform identity loads (accent, background, typography rules)  
4. Platform content loads  
5. Top layer appears (auto‑hide timer resets)  

## Entry Rules
Platform entry must:
- Always push a new stack entry  
- Never replace the Hub  
- Never skip the Hub  
- Never animate aggressively  
- Never shift layout  

## Entry Motion
Allowed:
- 120–150ms fade  
- 2–4px micro‑shift  

Prohibited:
- Slide  
- Bounce  
- Parallax  
- Scale  
- Rotation  

Platform entry must feel calm and cinematic.

---

# Platform Exit

Platform exit occurs when:
- The user presses the Hub button  
- The user unwinds the stack back to the Hub  
- A system event forces a return to Hub (rare, e.g., logout)  

## Exit Sequence (Hub Button)
1. Stack is cleared  
2. Hub becomes the only stack entry  
3. Platform identity is removed  
4. Hub loads  
5. Top layer appears  

## Exit Sequence (Back)
If the user unwinds the stack:
- Back pops pages until Hub is reached  
- Hub loads normally  
- Platform identity is removed at the moment Hub becomes active  

## Exit Rules
Platform exit must:
- Always return to Hub  
- Never switch directly to another platform  
- Never skip Hub  
- Never preserve platform identity after exit  

## Exit Motion
Same as entry:
- 120–150ms fade  
- No slide  
- No bounce  
- No parallax  

---

# Platform Root Page Behavior

The platform root page is the **first page** after entering a platform.

Rules:
- Must reflect platform identity  
- Must be deterministic  
- Must not auto‑navigate  
- Must not open modals automatically  
- Must not trigger platform switching  

The root page is the anchor of the platform world.

---

# Platform Sub‑Pages

Sub‑pages include:
- Game details  
- Music album pages  
- Video pages  
- Book pages  
- Event pages  

Sub‑pages:
- Push onto the stack  
- Never replace the root  
- Never collapse into the root  
- Never skip the root  

Back unwinds sub‑pages until the root is reached.

---

# Platform Identity Activation

Platform identity includes:
- Accent color  
- Background  
- Typography rules  
- Iconography rules  
- Motion rules  

Identity activates:
- Immediately upon platform entry  
- Before content loads  
- Before top layer auto‑hide timer begins  

Identity deactivates:
- Immediately upon platform exit  
- Before Hub loads  

Identity must never:
- Leak into the Hub  
- Leak into utility pages  
- Persist after exit  

---

# Platform Switching

Platform switching is **Hub‑only**.

Example:

Games → Wallet → Profile

User presses Hub:
Stack clears → Hub

User selects Music:
Hub → Music

Back:
Music → Hub

Back never returns to Games.

---

# Platform Exit Edge Cases

## 1. Modal Open
If a modal is open:
- Back closes the modal  
- A second Back unwinds the stack  

Platform exit never occurs while a modal is open.

## 2. Radial Wheel Open
If a wheel is open:
- Back closes the wheel  
- A second Back unwinds the stack  

## 3. Utility Page Open
Utility pages do not affect platform exit.

Example:
Games → Wallet → Legal

Back unwinds:
Legal → Wallet → Games → Hub

## 4. Forced Exit (Logout)
Logout forces:
- Stack clear  
- Return to Hub  
- Identity reset  

---

# Anti‑Patterns

Platform entry/exit must never:
- Skip the Hub  
- Switch platforms automatically  
- Use aggressive animation  
- Cause layout shift  
- Use platform identity on the Hub  
- Trigger modals automatically  
- Collapse stack entries  
- Adapt based on context  

These violate the EndlessOS navigation doctrine.

---

# Summary

Platform entry and exit define how users move between worlds in EndlessOS.

Platform entry:
- Is Hub‑initiated  
- Pushes a new stack entry  
- Activates platform identity  
- Uses calm, cinematic motion  

Platform exit:
- Returns to Hub  
- Clears identity  
- Never switches platforms directly  
- Never skips the Hub  

This ensures EndlessOS remains predictable, cinematic, and world‑driven.