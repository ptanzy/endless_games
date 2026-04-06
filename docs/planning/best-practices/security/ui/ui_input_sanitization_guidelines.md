# EndlessOS — UI Input Sanitization Guidelines

## Purpose
Defines how all user input must be sanitized before being processed, displayed, or transmitted.

---

# Core Principles

## 1. Sanitize at the UI Boundary
All input must be sanitized:
- on keystroke (optional)  
- on blur  
- before submission  
- before rendering  

---

## 2. Allowed Input Rules
UI must enforce:
- maximum length  
- allowed character sets  
- allowed formats  
- allowed patterns  

Reject everything else.

---

## 3. Rich Text Handling
If rich text is allowed:
- strip scripts  
- strip event handlers  
- strip inline styles  
- allow only whitelisted tags  

---

## 4. Paste Handling
On paste:
- sanitize content  
- remove formatting  
- remove embedded objects  
- remove hidden characters  

---

# Summary
Input sanitization prevents malicious content from entering the EndlessOS UI or backend.
