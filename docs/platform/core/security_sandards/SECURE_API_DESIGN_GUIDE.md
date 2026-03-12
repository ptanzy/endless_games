# SECURE_API_DESIGN_GUIDE

---

## 🎯 Purpose & Philosophy

This guide defines the **mandatory security standards for all EndlessGames APIs**.  
It ensures every service is:

- deterministic  
- safe by default  
- resistant to injection and tampering  
- compliant with Zero Moderation  
- compliant with child‑safety rules  
- predictable under load  
- testable and reviewable  
- ready for penetration testing  

These rules apply to **all backend services**, including:

- game servers  
- platform services  
- creator systems  
- brand systems  
- media systems  
- parental controls  
- authentication and identity  
- internal tools  

---

# 1. API CONTRACT PRINCIPLES

## 1.1 Deterministic Behavior
Every API must:

- return the same output for the same input  
- avoid nondeterministic branching  
- avoid hidden side effects  
- avoid time‑based randomness unless explicitly documented  

## 1.2 Strict Schema Enforcement
All APIs must:

- validate request bodies against a schema  
- reject unknown fields  
- reject incorrect types  
- reject unbounded strings  
- reject unbounded arrays  
- reject malformed JSON  

## 1.3 Versioning Rules
- All breaking changes require a new version  
- Versions must be explicit (`/v1/`, `/v2/`)  
- Old versions must be deprecated with a schedule  
- No silent contract changes  

---

# 2. INPUT VALIDATION & SANITIZATION

## 2.1 Mandatory Validation
Every input must be validated for:

- type  
- length  
- allowed characters  
- allowed ranges  
- allowed enum values  
- schema shape  

## 2.2 Reject Unsafe Input
Reject:

- free‑form text (child accounts)  
- unbounded strings  
- unbounded arrays  
- nested objects without schema  
- unknown fields  
- malformed JSON  

## 2.3 Never Trust the Client
Clients cannot enforce:

- permissions  
- cooldowns  
- pricing  
- limits  
- business rules  
- game rules  

All validation must be server‑side.

---

# 3. INJECTION PREVENTION

## 3.1 SQL Injection
- Use parameterized queries only  
- Never concatenate SQL strings  
- Never accept raw SQL from clients  
- Use ORM query builders when possible  

## 3.2 NoSQL Injection
- Validate all keys and values  
- Reject dynamic field names  
- Reject dynamic operators  
- Enforce strict schemas  

## 3.3 Command Injection
- Never pass user input to shell commands  
- Never use `exec`, `spawn`, or `eval` with dynamic input  
- Use safe libraries for file operations  

## 3.4 Template Injection
- Escape all template variables  
- Never pass raw user input into templates  

---

# 4. AUTHENTICATION & SESSION SECURITY

## 4.1 Token Rules
- Short‑lived access tokens  
- Rotating refresh tokens  
- Device binding  
- IP heuristics for suspicious activity  
- No tokens in localStorage  

## 4.2 Authentication Enforcement
Every API must:

- require authentication unless explicitly public  
- validate tokens on every request  
- validate device and session state  
- validate region and age restrictions  

## 4.3 Session Hardening
- Invalidate sessions on password change  
- Invalidate sessions on suspicious activity  
- Enforce session expiration  
- Enforce device‑level session limits  

---

# 5. AUTHORIZATION & PERMISSIONS

## 5.1 Server‑Side Enforcement Only
Never trust:

- client roles  
- client flags  
- client claims  
- client toggles  

## 5.2 Permission Layers
APIs must enforce:

- child vs adult  
- creator vs non‑creator  
- brand vs non‑brand  
- clan leader vs member  
- region restrictions  
- game access restrictions  

## 5.3 Principle of Least Privilege
Services and users must have the **minimum** permissions required.

---

# 6. RATE LIMITING & ABUSE PREVENTION

## 6.1 Required Limits
Every endpoint must have:

- per‑IP limits  
- per‑user limits  
- per‑device limits  
- per‑route limits  

## 6.2 Abuse Detection
APIs must detect:

- rapid repeated calls  
- suspicious patterns  
- brute force attempts  
- token cycling  
- replay attacks  

## 6.3 Automatic Blocking
On abuse detection:

- block the session  
- block the device  
- block the IP (temporary)  
- log the event  

---

# 7. ERROR HANDLING & RESPONSE SAFETY

## 7.1 Safe Error Responses
Errors must be:

- structured  
- typed  
- non‑verbose  
- non‑leaking  

Never expose:

- stack traces  
- internal service names  
- database schema  
- internal IDs  
- environment variables  

## 7.2 Error Codes
Use:

- `400` for validation errors  
- `401` for auth failures  
- `403` for permission failures  
- `404` for missing resources  
- `409` for conflicts  
- `429` for rate limits  
- `500` for internal errors  

---

# 8. LOGGING & MONITORING

## 8.1 Safe Logging
Never log:

- passwords  
- tokens  
- secrets  
- PII  
- child data  

## 8.2 Structured Logs
Logs must be:

- structured  
- typed  
- machine‑readable  
- scrubbed  

## 8.3 Monitoring Requirements
Monitor:

- auth failures  
- rate limit triggers  
- suspicious patterns  
- error bursts  
- traffic anomalies  

---

# 9. SECRETS & CONFIGURATION

## 9.1 Secrets Management
Never store secrets in:

- source code  
- config files  
- logs  
- client bundles  

Use a secret manager.

## 9.2 Environment Separation
- dev  
- staging  
- production  

No cross‑environment secrets.

---

# 10. DATA PROTECTION & PRIVACY

## 10.1 Child Data Rules
- No unnecessary child data stored  
- No child data logged  
- No child data shared  
- No child data used for personalization  

## 10.2 Encryption Rules
- TLS for all traffic  
- Encryption at rest  
- Modern cipher suites  

---

# 11. API TESTING REQUIREMENTS

## 11.1 Automated Tests
Every API must have:

- unit tests  
- integration tests  
- schema validation tests  
- permission tests  
- rate limit tests  
- error handling tests  

## 11.2 Security Tests
CI must include:

- static analysis  
- dynamic analysis  
- dependency scanning  
- fuzz testing (where applicable)  

## 11.3 Penetration Testing Readiness
APIs must be hardened against:

- SQL injection  
- NoSQL injection  
- XSS  
- CSRF  
- SSRF  
- RCE  
- IDOR  
- privilege escalation  
- replay attacks  
- session fixation  

---

# 12. SUCCESS CRITERIA

This guide is successful when:

- No injection vulnerabilities  
- No broken auth flows  
- No broken permission flows  
- No unsafe logs  
- All APIs pass pen tests  
- All APIs behave deterministically  
- All services follow strict schemas  
- All code is reviewable and maintainable  

