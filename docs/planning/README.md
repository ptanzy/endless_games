# Planning Documentation

The **planning pillar** defines *what the product should do* at a conceptual, behavioral, UX, and system‑design level.  
It is not implementation — that belongs in `/platform` and `/architecture`.

This pillar is organized into several major sections:

---

## 📁 Core Planning

### **doctrines/**
High‑level platform truths that guide all systems.  
Examples:
- ZERO_MODERATION_PLANNING.md  
- CORE_DOCTRINE_OVERVIEW.md  
- PLATFORM_DOCTRINE_OVERVIEW.md  

### **standards/**
Cross‑system requirements and constraints.  
Examples:
- PERFORMANCE_PLANNING.md  
- PERMISSIONS_MODEL.md  
- DATA_OWNERSHIP.md  
- SYSTEM_BOUNDARIES.md  

### **systems/**
Functional system planning documents.  
Examples:
- PROGRESSION_SYSTEM_PLANNING.md  
- ENDLESSEVENTS_PLANNING.md  
- ACHIEVEMENTS_SYSTEM_PLANNING.md  

---

## 📁 UI Planning

### **overview/**
High‑level UI philosophy and architecture.

### **carousel/**
Hub carousel, utility mini‑carousel, radial wheel, navigation hierarchy.

### **component/**
UI component specifications.

### **design/**
Color, typography, spacing, iconography, motion.

### **modal/**
Global modals, platform‑local modals, utility modals.

### **navigation/** *(recommended new folder)*
Navigation system, stack behavior, hub behavior, auto‑hide top layer.

### **backgrounds/** *(recommended new folder)*
Hub background, platform backgrounds, background packs.

### **layout/** *(recommended new folder)*
Hub layout, platform layout, utility layout, safe zones.

### **state/** *(optional folder)*
UI state machines (loading, empty, error).

### **accessibility/** *(optional folder)*
Contrast, reduced motion, text scaling.

---

## 📁 Tools & SDK

### **tools/**
Internal and creator‑facing tools.

### **tools/sdk/**
SDK tooling: validation pipeline, editor workflow, publishing console, templates, asset rules.

---

# 📄 Document Template

All planning docs should follow the master template:

See:  
`PLANNING_DOC_TEMPLATE.md`

This template defines:

- Required sections  
- Optional sections  
- When workflows, states, data models, APIs, safety, performance, or telemetry should be included  

---

# 🧭 When to Use Optional Sections

### **Workflows**
Include only for systems with sequential or state‑based behavior.

### **States**
Include for UI or systems with meaningful state transitions.

### **Data Model**
Include for systems with structured data (profile, membership, clans, events, progression).

### **API Surface**
Include for systems that expose APIs (SDK, identity, wallet, notifications).

### **Safety Rules**
Include for systems involving UGC or communication.

### **Performance Requirements**
Include for systems with runtime constraints.

### **Observability / Telemetry**
Include for systems that require analytics or monitoring.

---

# 📌 Purpose of the Planning Pillar

The planning pillar ensures:

- Consistency  
- Scalability  
- Predictability  
- Cross‑team clarity  
- Future‑proofing  
- Alignment with EndlessOS doctrines  

It is the foundation for `/platform` and `/architecture`.

