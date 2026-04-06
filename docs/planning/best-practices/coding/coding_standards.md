# coding standards

## Overview
Establish clear, consistent coding standards to improve code readability, maintainability, and collaboration.

## Best Practices
- Use a consistent naming convention (e.g., camelCase for variables, PascalCase for classes).
- Write self-documenting code; use meaningful variable and function names.
- Keep functions and methods short and focused on a single responsibility.
- Avoid deep nesting; use early returns to reduce complexity.
- Comment why, not what—explain intent, not obvious code.
- Remove dead code and unused variables regularly.
- Use version control for all code changes.

# EndlessOS — Coding Standards

## Purpose
Defines the global engineering standards for EndlessOS.  
All code must be deterministic, maintainable, predictable, and aligned with platform doctrine.

---

# Core Principles

## 1. Deterministic Behavior
Code must:
- Produce the same output for the same input  
- Avoid hidden state  
- Avoid time‑based randomness  
- Avoid context‑dependent behavior  

---

## 2. Predictable Structure
All files must follow:
- Consistent naming  
- Consistent folder structure  
- Consistent imports  
- Consistent component patterns  

---

## 3. Readability Over Cleverness
Readable code is preferred over:
- overly abstract patterns  
- clever one‑liners  
- unnecessary functional gymnastics  

---

# Naming Conventions

## Files
- Components: `ComponentName.tsx`  
- Hooks: `useThing.ts`  
- Utilities: `thingUtils.ts`  
- Types: `thing.types.ts`  

## Variables
- camelCase for variables  
- PascalCase for components  
- CONSTANT_CASE for constants  

---

# Imports
- Absolute imports for internal modules  
- Group imports by domain  
- No circular imports  

---

# Comments
- Use comments to explain *why*, not *what*  
- Avoid redundant comments  

---

# Summary
Coding standards ensure EndlessOS code remains predictable, readable, and maintainable across all teams.
