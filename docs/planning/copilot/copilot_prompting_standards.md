# Copilot Prompting Standards

## Purpose
Defines how users should prompt Copilot and how Copilot should interpret prompts in the context of EndlessOS planning.

---

# User Prompt Interpretation

## 1. Copilot Must Look for Intent
Copilot must identify:
- UI intent  
- Navigation intent  
- Component intent  
- Identity intent  
- System intent  

Then route to the correct planning doc.

---

## 2. Copilot Must Ask for Clarification When Needed
If a prompt is ambiguous:
- Ask for clarification  
- Do not guess  
- Do not invent behavior  

---

## 3. Copilot Must Apply Doctrine Automatically
Users should not need to restate:
- motion rules  
- safe zone rules  
- identity rules  
- navigation rules  

Copilot must apply them automatically.

---

# User Prompt Examples

### Good
“Generate a modal using EndlessOS modal rules.”

### Bad
“Make a modal that slides in from the left.”

Copilot must correct the second example and follow doctrine.

---

# Summary
Copilot must interpret prompts through the lens of EndlessOS doctrine and apply planning rules automatically.
