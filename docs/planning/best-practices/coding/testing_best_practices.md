# testing best practices

## Overview
Ensure code quality and reliability through comprehensive testing.

## Best Practices
- Write unit, integration, and end-to-end tests.
- Use test-driven development (TDD) where appropriate.
- Mock external dependencies in tests.
- Keep tests fast, isolated, and repeatable.
- Use descriptive test names and clear assertions.
- Run tests automatically on every commit (CI/CD).
- Measure code coverage and improve weak areas.

# EndlessOS — Testing Best Practices

## Purpose
Defines how to test EndlessOS code to ensure stability and deterministic behavior.

---

# Core Principles

## 1. Test Behavior, Not Implementation
- Avoid testing private logic  
- Test outcomes  

---

## 2. Snapshot UI
- Use snapshots for components  
- Ensure deterministic rendering  

---

## 3. Navigation Tests
- Test stack behavior  
- Test back button behavior  
- Test Hub resets  

---

# Summary
Testing ensures EndlessOS remains stable, predictable, and regression‑free.
