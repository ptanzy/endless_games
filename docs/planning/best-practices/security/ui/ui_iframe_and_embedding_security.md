# ui_iframe_and_embedding_security

Security best practices for iframes and embedded content:

- Use the sandbox attribute on all iframes.
- Restrict iframe origins with the allow attribute.
- Avoid embedding untrusted content.
- Disable unnecessary features (e.g., scripts, forms) in iframes.
- Monitor embedded content for changes or malicious activity.
- Implement X-Frame-Options and CSP frame-ancestors directives.

# EndlessOS — Iframe & Embedding Security

## Purpose
Defines how EndlessOS must securely embed external content using iframes or similar mechanisms.

---

# Core Principles

## 1. Use Strict Sandbox Attributes
All iframes must include:
- `sandbox="allow-same-origin allow-scripts"` (minimum)  
- No `allow-top-navigation`  
- No `allow-popups`  
- No `allow-forms` unless required  

---

## 2. Restrict Frame Origins
Use:
- `X-Frame-Options: DENY`  
- `frame-ancestors` CSP rules  

Only approved origins may embed EndlessOS content.

---

## 3. Prevent Clickjacking
- Use opaque overlays for sensitive actions  
- Disable pointer events when necessary  
- Never allow transparent overlays from external frames  

---

## 4. No Privileged Embeds
Iframes must never:
- access session data  
- access cookies  
- access local storage  
- access parent DOM  

---

# Summary
Embedding must be sandboxed, origin‑restricted, and isolated from EndlessOS UI and data.
