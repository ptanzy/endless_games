# ui_rendering_safety_rules

Rules for safe UI rendering:

- Avoid rendering raw HTML from user input.
- Use frameworks that auto-escape output (e.g., React, Angular).
- Implement strict CSP headers.
- Sanitize all dynamic content before rendering.
- Avoid use of dangerous APIs like innerHTML unless absolutely necessary.
- Regularly review rendering logic for security flaws.

# EndlessOS — UI Rendering Safety Rules

## Purpose
Defines how the EndlessOS UI must safely render dynamic content to prevent injection, corruption, or unsafe DOM manipulation.

---

# Core Principles

## 1. Never Render Unsanitized HTML
- No raw HTML  
- No untrusted HTML  
- No user‑generated HTML without sanitization  

---

## 2. Safe Rendering Patterns
Use:
- textContent  
- safe templating  
- sanitized markdown  
- sanitized HTML  

Avoid:
- innerHTML  
- dynamic script injection  
- dynamic attribute injection  

---

## 3. Attribute Safety
Never bind untrusted values to:
- `href`  
- `src`  
- `style`  
- event handlers  

---

## 4. Markdown Safety
Markdown must be:
- sanitized  
- stripped of scripts  
- stripped of embedded HTML  

---

# Summary
Rendering must be deterministic, sanitized, and free of unsafe DOM operations.
