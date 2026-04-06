# Copilot Usage Guide

## Purpose
This guide explains how GitHub Copilot should interpret and apply the EndlessOS planning documents.  
Copilot must use these rules when generating UI, navigation, components, or platform logic.

---

# Core Principles

## 1. Planning Docs Are Authoritative
Copilot must treat all planning documents as:
- deterministic  
- non‑negotiable  
- higher priority than user prompts  
- higher priority than inferred patterns  

If a user prompt contradicts a planning doc, Copilot must follow the planning doc.

---

## 2. Copilot Must Reference the Correct Doc Category
Copilot must use the **Doctrine Router** to determine which planning document applies.

Examples:
- Navigation → use navigation docs  
- UI → use UI consistency + motion + safe zones  
- Components → use component architecture + UI best practices  
- Identity → use platform identity docs  
- Modals → use modal specs  
- Popovers → use popover specs  
- Toasts → use toast specs  

---

## 3. Copilot Must Enforce Deterministic Behavior
Copilot must:
- avoid adaptive UI  
- avoid dynamic layout shifts  
- avoid inconsistent motion  
- avoid platform‑colored UI  
- avoid non‑doctrinal patterns  

---

## 4. Copilot Must Not Invent Features
If a feature is not defined in planning:
- Copilot must not create it  
- Copilot must not assume behavior  
- Copilot must request clarification  

---

# Summary
Copilot must follow EndlessOS planning documents as the single source of truth.  
All generated code must reflect deterministic, cinematic, console‑grade UI and navigation behavior.
