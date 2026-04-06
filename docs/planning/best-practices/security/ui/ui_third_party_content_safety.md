# ui_third_party_content_safety

Best practices for handling third-party content in the UI:

- Only use trusted third-party sources.
- Sanitize and validate all third-party data before rendering.
- Restrict permissions and access for third-party scripts.
- Monitor and audit third-party integrations regularly.
- Use subresource integrity (SRI) for external scripts and styles.
- Isolate third-party content using iframes with proper sandboxing.

# EndlessOS — Third‑Party Content Safety

## Purpose
Defines how EndlessOS must handle third‑party content, embeds, widgets, and external scripts.

---

# Core Principles

## 1. Avoid Third‑Party Scripts
- No external JS unless explicitly approved  
- No inline scripts from third parties  
- No dynamic script injection  

---

## 2. Sandbox All External Content
Use:
- sandboxed iframes  
- restrictive CSP  
- blocked script execution  
- blocked form submission  

---

## 3. Validate External Origins
Only allow:
- trusted domains  
- approved CDNs  
- version‑pinned assets  

Reject everything else.

---

## 4. No Third‑Party DOM Access
Third‑party content must never:
- access the EndlessOS DOM  
- read cookies  
- read local storage  
- access session data  

---

# Summary
Third‑party content must be isolated, sandboxed, and prevented from interacting with EndlessOS internals.
