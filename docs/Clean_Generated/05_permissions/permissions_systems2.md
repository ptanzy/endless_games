# PERMISSION SYSTEM

## Purpose
Define what actions each actor can perform.

---

## Roles

### Player
- Play games
- Consume content
- Limited interaction

### Creator
- Upload content
- Monetize
- Access creator tools

### System
- Execute automated actions

---

## Permission Model

Permissions are:

- Explicit
- Non-inheritable unless defined
- Context-based

---

## Example

Action: "Start Stream"

Requirements:
- Role: Creator
- Verified identity
- Not rate-limited

---

## Enforcement

Permissions are checked:
- At API layer
- Before execution

No UI-only restrictions allowed.