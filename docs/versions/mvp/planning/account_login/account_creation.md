# MVP Account Creation – Planning Document

## 1. Purpose
Define the minimum account creation flow required for players to join EndlessGames.  
This system must be simple, secure, familiar, and fast to build with GitHub Copilot.  
It introduces no identity surfaces, no profiles, and no advanced account features.

The goal is to enable users to:
- Create an account  
- Automatically authenticate  
- Access the Games Page  

Nothing more.

---

## 2. Goals
- Support account creation using **email, username, and password**.
- Enforce **unique email** and **unique username**.
- Provide a clean, familiar UI that users instantly understand.
- Automatically authenticate users after successful registration.
- Redirect users to the **Games Page**.
- Keep the flow lightweight, secure, and MVP‑appropriate.
- Establish a foundation for future identity and account systems.

---

## 3. Non‑Goals
These features are **explicitly excluded** from MVP:
- No CAPTCHA (checkbox or puzzles).
- No Google, Apple, Facebook, or third‑party logins.
- No email verification.
- No password reset flow.
- No profile, avatar, or identity surfaces.
- No display name separate from username.
- No social features.
- No parental controls.
- No multi‑step onboarding.
- No advanced password strength meters.
- No terms‑of‑service modal or legal gating beyond a simple checkbox.

These will be introduced in later releases when the identity layer is built.

---

## 4. Core Capabilities

### 4.1 Required Inputs
Users must provide:
- **Email**  
- **Username**  
- **Password**  
- **Verify Password** (optional but recommended)  

### 4.2 System Requirements
The system must:
- Validate email format  
- Validate username format  
- Ensure email is unique  
- Ensure username is unique  
- Validate password meets minimal requirements  
- Hash and store the password  
- Automatically authenticate the user  
- Redirect to the Games Page  

---

## 5. UI Requirements

### 5.1 Create Account Page
A simple, familiar layout:
- Header: **Create Account**
- Email field  
- Username field  
- Password field  
- Verify Password field  
- Simple password requirements list  
- Primary button: **Create Account**
- Link: **Sign In**

### 5.2 Password Requirements (MVP)
Keep requirements simple and non‑intimidating:
- Minimum length (e.g., 6–8 characters)
- No complex strength rules
- No dynamic strength meter

The goal is low friction, not high security.

---

## 6. Rules

### 6.1 Email Rules
- Must be unique  
- Must be valid format  
- Case‑insensitive uniqueness  

### 6.2 Username Rules
- Must be unique  
- 3–20 characters  
- Letters, numbers, underscores  
- Case‑insensitive uniqueness  
- No spaces  

### 6.3 Password Rules
- Minimum length requirement  
- Must match “Verify Password”  
- No advanced complexity rules in MVP  

### 6.4 Terms & Conditions
- User must check the agreement box  
- No modal or legal gating in MVP  

### 6.5 Authentication Rules
- Successful account creation logs the user in automatically  
- User is redirected to the Games Page  

---

## 7. Constraints
- No CAPTCHA in MVP.  
- No email verification.  
- No password reset.  
- No third‑party authentication providers.  
- No identity surfaces (profile, avatar, display name).  
- No multi‑step onboarding.  
- No advanced security features beyond basic best practices.  
- No storage of plaintext passwords.  

---

## 8. Workflows

### 8.1 Account Creation Flow
1. User selects “Create Account”.  
2. User enters email, username, password, verify password.  
3. User checks the terms & conditions box.  
4. System validates:
   - email format  
   - username format  
   - password requirements  
   - email uniqueness  
   - username uniqueness  
5. System creates the account.  
6. User is automatically authenticated.  
7. User is redirected to the Games Page.

---

### 8.2 Error Handling
- If email is already used → show simple error  
- If username is taken → show simple error  
- If password doesn’t meet requirements → show simple error  
- If passwords don’t match → show simple error  
- Errors should be clear, non‑technical, and friendly  

---

## 9. Success Criteria
- Users can create accounts without friction.  
- Duplicate emails/usernames are prevented.  
- Password requirements are simple and easy to meet.  
- Users are automatically logged in after registration.  
- Users reach the Games Page reliably.  
- The UI feels familiar, simple, and trustworthy.  
- The system is small enough for GitHub Copilot to help build efficiently.  

---

## 10. Future Hooks (Not Implemented in MVP)
- Email verification  
- Password reset  
- Third‑party login providers  
- Identity system (profile, avatar, display name)  
- Membership system  
- Economy and progression  
- Multi‑device account linking  
- Parental controls  
- Social features  
- Passkeys and MFA  
- Optional CAPTCHA if abuse appears  
- Checkbox: “I agree to the terms and conditions”
