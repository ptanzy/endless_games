# EndlessOS — Frontend Security Best Practices

## Purpose
Defines the security rules required to protect the EndlessOS UI from client‑side attacks, unsafe rendering, and malicious user input.

---

# Core Principles

## 1. Never Trust Client Input
All UI input must be:
- validated  
- sanitized  
- length‑checked  
- type‑checked  

The UI must never assume user input is safe.

---

## 2. Prevent XSS
- Escape all dynamic content  
- Never inject raw HTML  
- Use safe templating  
- Sanitize user‑generated content  
- Avoid `dangerouslySetInnerHTML` unless explicitly approved  

---

## 3. Prevent CSRF
- Use same‑site cookies  
- Use CSRF tokens for state‑changing requests  
- Never rely on client‑side checks alone  

---

## 4. Prevent Clickjacking
- Use `X-Frame-Options: DENY`  
- Use `frame-ancestors` CSP rules  
- Avoid embedding untrusted content  

---

## 5. Protect Sensitive UI States
- Never expose auth state in the DOM  
- Never store tokens in JS‑accessible storage  
- Never leak session identifiers  

---

# Summary
Frontend security protects EndlessOS from injection, tampering, and session abuse.  
All UI code must follow these rules without exception.
