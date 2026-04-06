# Copilot Navigation Rules Reference

## Purpose
A distilled reference of EndlessOS navigation doctrine for Copilot.

---

# Core Navigation Rules

## 1. Stack Behavior
- Push for forward navigation  
- Pop for back  
- Clear when returning to Hub  
- No adaptive navigation  

## 2. Back Button
- Pops stack  
- Closes modals first  
- Closes wheels before popping  

## 3. Hub Behavior
- Hub is stack root  
- Hub resets identity  
- Hub resets scroll  

## 4. Scroll Rules
- New pages → scroll to top  
- Returning pages → restore scroll  
- Modals/wheels → preserve scroll  

## 5. Motion Rules
- Fade + micro‑shift only  
- No slide transitions  

---

# Summary
Copilot must apply these navigation rules to all routing, transitions, and page logic.
