# EndlessOS — Authentication & Session Best Practices

## Purpose
Defines how authentication and session management must be implemented securely.

---

# Core Principles

## 1. Secure Token Handling
- HTTP‑only cookies  
- same‑site restrictions  
- no localStorage tokens  

---

## 2. Short Session Lifetimes
- short‑lived tokens  
- secure refresh  
- immediate revocation  

---

## 3. Password Security
- strong hashing  
- no plaintext  
- strong password rules  

---

# Summary
Authentication must be safe, token‑based, and resistant to hijacking.
