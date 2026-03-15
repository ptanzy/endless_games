# Movement Engine Specification

This document outlines the requirements and design for the chess movement engine.# MOVEMENT ENGINE SPECIFICATION

## Overview
The Movement Engine is responsible for interpreting movement rules across all board architectures (Single Board, Stacked Boards, Cube, Matrix). It processes movement vectors, validates legality, checks blocking, and resolves captures.

---

## Core Responsibilities
- Interpret movement rules selected during match creation  
- Validate movement vectors for each piece  
- Apply blocking and line-of-sight rules  
- Handle vertical and 3D movement  
- Resolve captures  
- Integrate portals and terrain effects  
- Support variant mechanics (Decoration, Recruitment, etc.)

---

## Movement Processing Pipeline

### 1. Input
- Piece type  
- Starting coordinate  
- Target coordinate  
- Board topology  
- Active rule modules  

### 2. Vector Validation
- Determine if the movement vector is legal for the piece  
- Apply 2D, vertical-only, or full 3D vector rules  

### 3. Blocking & Line-of-Sight
- Apply blocking rules:
  - 2D blocking  
  - 3D blocking  
  - Portal bypass  
  - Terrain bypass  

### 4. Capture Resolution
- Determine if target square contains:
  - Enemy piece  
  - Friendly piece  
  - Neutral piece  
  - Portal  
  - Terrain hazard  

### 5. Special Rules
- Pawn movement mode  
- Knight 3D jumps  
- King adjacency in 3D  
- Decoration rule (gain powers)  
- Recruitment rule (captured pieces join)  

---

## Coordinate System
Supports:
- 2D coordinates (x, y)  
- Layered coordinates (x, y, z)  
- Cube face coordinates  
- Matrix coordinates  

---

## Blocking Rules
### 1. 2D Blocking
- Only checks current layer.

### 2. 3D Blocking
- Checks all axes.

### 3. Portal Bypass
- Portals may ignore blocking depending on rule settings.

---

## Vertical Movement
- Vertical transitions validated via:
  - Alignment rules  
  - Cost rules  
  - Blocking rules  

---

## Error Handling
- Illegal move  
- Out-of-bounds  
- Blocked path  
- Invalid vector  
- Terrain hazard  

---

## Notes
The Movement Engine is the most interconnected subsystem and must remain modular to support future variants.

