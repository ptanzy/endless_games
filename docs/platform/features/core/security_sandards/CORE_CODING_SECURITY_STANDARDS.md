# CORE_CODING_SECURITY_STANDARDS

---

## 🎯 Purpose & Philosophy

This document defines the **mandatory coding security standards** for all EndlessGames services, games, tools, and platform components. These rules ensure:

- Zero‑moderation safety  
- Predictable, deterministic backend behavior  
- Protection against injection attacks  
- Secure authentication and session handling  
- Safe data validation and sanitization  
- Compliance with child‑safety and privacy laws  
- Resistance to penetration testing  
- Defense‑in‑depth across all layers  
- Maintainable, reviewable, testable code  

These standards apply to **all languages, all services, all teams, all environments**.

---

# 1. INPUT VALIDATION & SANITIZATION

## 1.1 Mandatory Validation Rules
All external input must be:

- validated  
- sanitized  
- type‑checked  
- length‑checked  
- pattern‑checked  
- schema‑validated  

No exceptions.

## 1.2 Never Trust Client Input
Clients may not:

- enforce business rules  
- enforce permissions  
- enforce limits  
- enforce pricing  
- enforce cooldowns  

All validation must occur server‑side.

## 1.3 Allowed Input Types
Only accept:

- enums  
- booleans  
- bounded integers  
- bounded floats  
- bounded strings  
- validated JSON objects  
- validated arrays  

No free‑form text for child accounts.  
No unbounded strings anywhere.

---

# 2. INJECTION PREVENTION

## 2.1 SQL Injection
- Always use parameterized queries  
- Never concatenate SQL strings  
- Never accept raw SQL from clients  
- Use ORM query builders where possible  

## 2.2 NoSQL Injection
- Validate all keys and values  
- Never pass client‑controlled objects directly into queries  
- Enforce strict schema validation  

## 2.3 Command Injection
- Never pass user input into shell commands  
- Never use `exec`, `spawn`, or `eval` with dynamic input  
- Use safe libraries for file operations  

## 2.4 Template Injection
- Never pass raw user input into templates  
- Escape all variables  
- Use safe template engines  

---

# 3. AUTHENTICATION & SESSION SECURITY

## 3.1 Token Rules
- Use short‑lived access tokens  
- Use rotating refresh tokens  
- Use device binding  
- Use IP heuristics for suspicious behavior  
- Never store tokens in localStorage  

## 3.2 Password Rules
- Never store plaintext passwords  
- Use strong hashing (bcrypt/argon2)  
- Enforce minimum complexity  
- Enforce rate limiting on login attempts  

## 3.3 Session Rules
- Invalidate sessions on password change  
- Invalidate sessions on suspicious activity  
- Enforce session expiration  
- Enforce device‑level session limits  

---

# 4. AUTHORIZATION & PERMISSIONS

## 4.1 Server‑Side Enforcement
All permissions must be enforced server‑side:

- child vs adult  
- creator vs non‑creator  
- brand vs non‑brand  
- clan leader vs member  
- region restrictions  
- game access restrictions  

## 4.2 Principle of Least Privilege
Services and users must have the **minimum** permissions required.

## 4.3 No Implicit Trust
Never trust:

- client claims  
- client roles  
- client flags  
- client‑side toggles  

---

# 5. API CONTRACT SAFETY

## 5.1 Deterministic Contracts
All APIs must:

- be deterministic  
- have stable schemas  
- have versioning  
- reject unknown fields  
- enforce strict typing  

## 5.2 Error Handling
Errors must be:

- structured  
- typed  
- non‑leaking  
- non‑verbose  
- safe for clients  

Never expose:

- stack traces  
- internal service names  
- database schema  
- internal IDs  

## 5.3 Rate Limiting
All endpoints must have:

- per‑IP limits  
- per‑user limits  
- per‑device limits  
- per‑route limits  

---

# 6. SECRETS MANAGEMENT

## 6.1 Never Hardcode Secrets
Secrets must never appear in:

- source code  
- config files  
- logs  
- client bundles  

## 6.2 Use a Secret Manager
All secrets must be stored in:

- Azure Key Vault  
- AWS Secrets Manager  
- GCP Secret Manager  

## 6.3 Rotation Rules
- Rotate secrets regularly  
- Rotate on breach suspicion  
- Rotate on employee offboarding  

---

# 7. DEPENDENCY HYGIENE

## 7.1 Approved Dependencies Only
All dependencies must:

- be approved  
- be maintained  
- have no known CVEs  
- be pinned to exact versions  

## 7.2 No Abandoned Libraries
Remove libraries that:

- are unmaintained  
- have unresolved security issues  
- have no active community  

## 7.3 Automated Scanning
CI/CD must run:

- SCA (Software Composition Analysis)  
- CVE scanning  
- License compliance checks  

---

# 8. CI/CD SECURITY

## 8.1 Build Pipeline Rules
- No secrets in CI logs  
- No untrusted build steps  
- No external scripts without review  
- Immutable build artifacts  

## 8.2 Deployment Rules
- Deploy from clean, reproducible builds  
- Enforce environment parity  
- Enforce automated tests  
- Enforce security gates  

## 8.3 Access Control
- MFA required  
- Role‑based access  
- No shared accounts  
- No persistent admin sessions  

---

# 9. LOGGING & MONITORING

## 9.1 Safe Logging
Never log:

- passwords  
- tokens  
- secrets  
- PII  
- child data  

## 9.2 Structured Logs
Logs must be:

- structured  
- typed  
- machine‑readable  
- scrubbed  

## 9.3 Monitoring Rules
Monitor:

- auth failures  
- suspicious patterns  
- rate limit triggers  
- unusual traffic spikes  
- error bursts  

---

# 10. PENETRATION TESTING READINESS

## 10.1 Required Hardening
All services must be hardened against:

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

## 10.2 Automated Testing
CI must include:

- static analysis  
- dynamic analysis  
- dependency scanning  
- fuzz testing (where applicable)  

## 10.3 Manual Testing
Quarterly:

- internal pen tests  
- external pen tests  
- red team exercises  

---

# 11. MEMORY & RESOURCE SAFETY

## 11.1 Memory Rules
- Avoid unbounded memory usage  
- Avoid unbounded recursion  
- Avoid unbounded loops  
- Enforce timeouts  

## 11.2 Resource Rules
- Enforce CPU limits  
- Enforce memory limits  
- Enforce request timeouts  
- Enforce concurrency limits  

---

# 12. DATA PROTECTION & PRIVACY

## 12.1 Child Data Rules
- No unnecessary child data stored  
- No child data logged  
- No child data shared  
- No child data used for personalization  

## 12.2 Encryption Rules
- Encrypt data in transit  
- Encrypt data at rest  
- Use modern TLS versions  

---

# 13. SAFE DEFAULTS

## 13.1 Default Deny
All systems must default to:

- deny access  
- deny permissions  
- deny unsafe input  
- deny unknown fields  

## 13.2 Fail Closed
On error:

- deny the action  
- do not assume success  
- do not assume permissions  

---

# 14. SUCCESS CRITERIA

This document is successful when:

- No injection vulnerabilities  
- No leaked secrets  
- No unsafe logs  
- No broken auth flows  
- No broken permission flows  
- All services pass pen tests  
- All APIs behave deterministically  
- All code is reviewable and maintainable  

