# state management best practices

## Overview
Manage application state in a predictable, scalable, and maintainable way.

## Best Practices
- Use a single source of truth for application state.
- Prefer immutable state updates.
- Use selectors and derived data to minimize recomputation.
- Keep state as flat as possible; avoid deeply nested structures.
- Separate UI state from business logic state.
- Use middleware for side effects and async logic.
- Persist only necessary state; avoid over-persisting transient data.

# EndlessOS — State Management Best Practices

## Purpose
Defines how state must be managed across EndlessOS to ensure deterministic behavior.

---

# Core Principles

## 1. Minimize Global State
- Use global state only for identity, auth, and platform‑level data  
- Avoid global UI state  

---

## 2. Prefer Local State
- Use local state for component‑specific behavior  
- Avoid unnecessary context providers  

---

## 3. Avoid Derived State
- Compute values on the fly  
- Do not store redundant state  

---

## 4. Avoid Race Conditions
- Use async/await  
- Avoid overlapping requests  
- Cancel stale requests  

---

# Summary
State must be minimal, predictable, and free of race conditions.
