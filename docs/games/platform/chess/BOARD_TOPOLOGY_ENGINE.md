# Board Topology Engine

This document explains the structure and topology of the chess board.# BOARD TOPOLOGY ENGINE

## Overview
Defines how the board is structured, how edges connect, and how movement wraps or transitions across layers.

---

## Supported Topologies

### 1. Single Board
- Standard 2D grid  

### 2. Stacked Boards
- Vertical adjacency  
- Edge alignment rules  

### 3. Cube Mode
- Face adjacency  
- Edge wrapping  
- Orientation mapping  

### 4. Matrix Mode
- Full 3D grid  
- No wrapping unless enabled  

### 5. Fan-Fold Mode
- Hinged layers  
- Folded adjacency  

### 6. Torus Mode
- Horizontal and vertical wrapping  

---

## Responsibilities
- Validate adjacency  
- Map coordinates across edges  
- Handle portals  
- Handle terrain changes  
- Provide topology-aware movement data  

---

## Edge Mapping
- Straight wrap  
- Rotated wrap  
- Mirrored wrap  

---

## Layer Transitions
- Vertical alignment  
- Portal-based transitions  
- Terrain-based transitions  

---

## Notes
The topology engine is foundational for all 3D and variant modes.

