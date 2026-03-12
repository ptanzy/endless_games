# SECURE_FRONTEND_CODING_GUIDE

---

## 🎯 Purpose & Philosophy

This guide defines the **mandatory security standards for all EndlessGames frontend code**, including:

- React/TypeScript web clients  
- Game clients  
- Creator tools (adult‑only)  
- Brand surfaces (adult‑only)  
- Parental dashboards  
- EndlessHub  
- Media surfaces (adult‑only)  

The goals:

- Prevent XSS, CSRF, clickjacking, and injection  
- Ensure deterministic, predictable UI behavior  
- Enforce child‑safe defaults  
- Protect tokens and session data  
- Avoid unsafe browser APIs  
- Maintain Zero Moderation compliance  
- Ensure all clients pass penetration testing  

These rules apply to **all frontend code**, regardless of framework or platform.

---

# 1. GENERAL FRONTEND SECURITY PRINCIPLES

## 1.1 Never Trust Client Input
Frontend code must assume:

- all input is untrusted  
- all input can be tampered with  
- all client‑side checks can be bypassed  

The server must enforce all business rules.

## 1.2 No Sensitive Logic in the Client
Never implement:

- permission checks  
- pricing logic  
- cooldowns  
- game rules  
- entitlement logic  
- age checks  
- region checks  

These must be server‑side only.

## 1.3 Deterministic UI Behavior
Frontend code must avoid:

- nondeterministic branching  
- hidden state mutations  
- race conditions  
- unpredictable rendering  

---

# 2. XSS PREVENTION

## 2.1 Never Inject Raw HTML
Never use:

- `dangerouslySetInnerHTML`  
- `innerHTML`  
- `document.write`  
- template string HTML injection  

Unless the content is:

- system‑generated  
- sanitized  
- explicitly approved  

## 2.2 Escape All Dynamic Content
All dynamic values must be escaped before rendering.

## 2.3 No User‑Generated HTML
Child accounts cannot generate content.  
Adult accounts cannot inject HTML.

---

# 3. CSRF & CLICKJACKING PROTECTION

## 3.1 CSRF Protection
All state‑changing requests must:

- use same‑site cookies  
- include anti‑CSRF tokens  
- use POST/PUT/PATCH/DELETE only  

## 3.2 Clickjacking Protection
Frontend must not allow:

- iframe embedding  
- frame nesting  
- external framing  

Unless explicitly approved for brand integrations.

---

# 4. TOKEN & SESSION SAFETY

## 4.1 Never Store Tokens in LocalStorage
LocalStorage is vulnerable to XSS.

Allowed storage:

- HttpOnly cookies  
- Secure cookies  
- In‑memory storage  

## 4.2 No Long‑Lived Tokens
Frontend must:

- refresh tokens regularly  
- rotate tokens  
- clear tokens on logout  
- clear tokens on tab close (optional)  

## 4.3 Device Binding
Frontend must include device identifiers for server‑side validation.

---

# 5. SAFE STATE MANAGEMENT

## 5.1 No Sensitive Data in Redux/Context
Never store:

- tokens  
- secrets  
- PII  
- child data  
- permissions  
- entitlements  

## 5.2 Immutable State Rules
State must be:

- predictable  
- serializable  
- free of side effects  

## 5.3 No Hidden Global State
Avoid:

- global variables  
- window‑attached state  
- implicit singletons  

---

# 6. NETWORK SECURITY

## 6.1 HTTPS Only
All requests must use HTTPS.

## 6.2 Strict API Contracts
Frontend must:

- validate API responses  
- reject unknown fields  
- reject malformed responses  
- handle version mismatches gracefully  

## 6.3 No Client‑Side Retry Storms
Implement:

- exponential backoff  
- retry limits  
- circuit breakers  

---

# 7. INPUT HANDLING & FORM SAFETY

## 7.1 Validate All Input
Frontend must validate:

- type  
- length  
- allowed characters  
- patterns  

## 7.2 No Free‑Form Text for Child Accounts
Child accounts cannot:

- type messages  
- type bios  
- type comments  
- type names (preset only)  

## 7.3 Adult Text Input Must Be Sanitized
Adult text fields must:

- strip HTML  
- strip scripts  
- strip emojis if needed  
- enforce length limits  

---

# 8. UI SECURITY & SAFE RENDERING

## 8.1 No Dynamic Script Loading
Never load scripts from:

- user input  
- unknown domains  
- untrusted CDNs  

## 8.2 No Inline Scripts
Avoid:

- inline event handlers  
- inline JS  
- inline CSS with dynamic values  

## 8.3 Safe Component Composition
Components must:

- avoid prop drilling of sensitive data  
- avoid unsafe refs  
- avoid direct DOM manipulation  

---

# 9. CHILD‑SAFE FRONTEND RULES

## 9.1 No Media Surfaces
Child accounts cannot access:

- EndlessTube  
- EndlessStream  
- EndlessTV  
- EndlessRadio  
- Creator pages  
- Brand pages  

## 9.2 No Public Visibility
Child accounts cannot:

- appear in leaderboards  
- appear in public lists  
- appear in search  
- appear in comments  
- appear in creator feeds  

## 9.3 No Uploads
Child accounts cannot upload:

- images  
- audio  
- video  
- text  

---

# 10. ERROR HANDLING & FAIL‑SAFE BEHAVIOR

## 10.1 Safe Error Messages
Frontend must not display:

- stack traces  
- internal IDs  
- server messages  
- raw error objects  

## 10.2 Fail Closed
On error:

- deny the action  
- show a safe fallback  
- never assume success  

---

# 11. DEPENDENCY SAFETY

## 11.1 Approved Libraries Only
Frontend may only use:

- vetted libraries  
- maintained libraries  
- libraries with no known CVEs  

## 11.2 Pin Versions
All dependencies must be pinned to exact versions.

## 11.3 Automated Scanning
CI must run:

- dependency scanning  
- CVE checks  
- license checks  

---

# 12. PENETRATION TESTING READINESS

Frontend must be hardened against:

- XSS  
- CSRF  
- clickjacking  
- DOM‑based injection  
- token theft  
- session fixation  
- replay attacks  
- UI redressing  
- open redirects  

---

# 13. SUCCESS CRITERIA

This guide is successful when:

- No XSS vulnerabilities  
- No CSRF vulnerabilities  
- No token leaks  
- No unsafe rendering  
- No child‑safety violations  
- All clients pass pen tests  
- All code is deterministic and reviewable  

