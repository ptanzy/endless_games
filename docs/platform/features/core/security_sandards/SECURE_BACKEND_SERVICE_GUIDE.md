# SECURE_BACKEND_SERVICE_GUIDE

---

## 🎯 Purpose & Philosophy

This guide defines the **mandatory security standards for all EndlessGames backend services**, including:

- platform microservices  
- game backend services  
- creator ecosystem services  
- brand systems  
- media processing services  
- parental control services  
- authentication & identity  
- internal tools and admin services  

Backend services are the authoritative source of truth.  
They must be **deterministic**, **tamper‑resistant**, **safe by default**, and **fully compliant with Zero Moderation and child‑safety rules**.

---

# 1. SERVICE ARCHITECTURE PRINCIPLES

## 1.1 Deterministic Behavior
Services must:

- produce the same output for the same input  
- avoid nondeterministic branching  
- avoid hidden side effects  
- avoid time‑based randomness unless explicitly documented  

## 1.2 Stateless by Default
Services should be:

- stateless  
- horizontally scalable  
- session‑agnostic  

State must live in:

- databases  
- caches  
- queues  
- event logs  

## 1.3 Explicit Contracts
Every service must define:

- request schemas  
- response schemas  
- error schemas  
- versioning rules  
- rate limits  

---

# 2. INPUT VALIDATION & SANITIZATION

## 2.1 Mandatory Validation
All inputs must be validated for:

- type  
- length  
- allowed characters  
- allowed ranges  
- allowed enum values  
- schema shape  

## 2.2 Reject Unknown Fields
Unknown fields must be rejected, not ignored.

## 2.3 Reject Unbounded Data
Reject:

- unbounded strings  
- unbounded arrays  
- nested objects without schema  
- free‑form text (child accounts)  

---

# 3. INTER‑SERVICE COMMUNICATION SECURITY

## 3.1 Mutual Authentication
All services must authenticate using:

- mTLS  
- service identities  
- signed tokens  

## 3.2 Authorization
Services must enforce:

- role‑based access  
- service‑level permissions  
- least privilege  

## 3.3 No Implicit Trust
Never trust:

- internal traffic  
- internal IPs  
- internal headers  

## 3.4 Request Signing
Critical operations must use:

- signed requests  
- nonce validation  
- replay protection  

---

# 4. DATABASE & STORAGE SAFETY

## 4.1 Query Safety
All queries must:

- use parameterized statements  
- enforce schema validation  
- reject dynamic field names  
- reject dynamic operators  

## 4.2 Data Access Rules
Services may only access:

- their own tables  
- their own collections  
- their own buckets  

No cross‑service database access.

## 4.3 Data Minimization
Store only what is required.

Especially for:

- child accounts  
- parental data  
- authentication data  

---

# 5. AUTHENTICATION & SESSION SECURITY

## 5.1 Token Validation
Services must validate:

- token signature  
- token expiration  
- token issuer  
- token audience  
- device binding  
- region restrictions  
- age restrictions  

## 5.2 Session Hardening
Services must:

- invalidate sessions on suspicious activity  
- enforce session expiration  
- enforce device‑level session limits  

---

# 6. AUTHORIZATION & PERMISSION ENFORCEMENT

## 6.1 Server‑Side Enforcement Only
Never trust:

- client roles  
- client flags  
- client claims  

## 6.2 Permission Layers
Services must enforce:

- child vs adult  
- creator vs non‑creator  
- brand vs non‑brand  
- region restrictions  
- game access restrictions  

## 6.3 No Implicit Permissions
All permissions must be explicit.

---

# 7. RATE LIMITING & ABUSE PREVENTION

## 7.1 Required Limits
Every service must enforce:

- per‑IP limits  
- per‑user limits  
- per‑device limits  
- per‑route limits  

## 7.2 Abuse Detection
Detect:

- brute force  
- token cycling  
- replay attacks  
- malformed payload floods  
- suspicious patterns  

## 7.3 Automatic Blocking
On abuse:

- block session  
- block device  
- block IP (temporary)  
- log event  

---

# 8. ERROR HANDLING & RESPONSE SAFETY

## 8.1 Safe Error Responses
Never expose:

- stack traces  
- internal service names  
- database schema  
- internal IDs  
- environment variables  

## 8.2 Structured Errors
Errors must be:

- typed  
- structured  
- deterministic  
- safe for clients  

---

# 9. LOGGING & MONITORING

## 9.1 Safe Logging
Never log:

- passwords  
- tokens  
- secrets  
- PII  
- child data  

## 9.2 Required Logging
Log:

- auth failures  
- permission failures  
- rate limit triggers  
- suspicious patterns  
- internal errors  

## 9.3 Monitoring
Monitor:

- latency  
- error rates  
- traffic anomalies  
- resource spikes  
- container restarts  

---

# 10. SECRETS & CONFIGURATION

## 10.1 Secret Manager Required
All secrets must be stored in:

- cloud secret manager  
- HSM for sensitive keys  

## 10.2 No Secrets in Code
Never store secrets in:

- source code  
- config files  
- logs  
- client bundles  

## 10.3 Rotation Rules
Rotate secrets:

- regularly  
- after offboarding  
- after suspicious activity  

---

# 11. GAME SERVER SECURITY (BACKEND‑SIDE)

## 11.1 Authoritative State
Game servers must:

- reject client‑side state  
- enforce authoritative logic  
- validate all actions  

## 11.2 Packet Safety
Reject:

- tampered packets  
- replayed packets  
- malformed packets  
- oversized packets  

## 11.3 Anti‑Cheat Enforcement
Backend must enforce:

- cooldowns  
- movement limits  
- inventory rules  
- currency rules  

---

# 12. CHILD‑SAFETY BACKEND RULES

## 12.1 No Public Visibility
Child accounts must never appear in:

- leaderboards  
- search  
- public lists  
- creator surfaces  
- brand surfaces  

## 12.2 No Uploads
Child accounts cannot upload:

- images  
- audio  
- video  
- text  

## 12.3 No Communication Vectors
Backend must reject:

- text fields  
- metadata fields  
- hidden channels  

---

# 13. ZERO MODERATION BACKEND RULES

## 13.1 No User‑Generated