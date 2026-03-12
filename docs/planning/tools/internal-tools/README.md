# Internal Tools — Planning Overview

---

## 🎯 Purpose

The **internal-tools** planning folder defines the conceptual design, workflows, and requirements for all internal content‑creation tools used across EndlessGames.  
These tools empower internal teams — artists, designers, brand partners, content managers, and internal creators — to safely and efficiently produce platform content without engineering involvement.

This folder contains **planning documents**, not implementation details.  
Each document describes *what the tool must do*, *why it exists*, and *how teams will use it*.

---

# 1. Scope of Internal Tools

Internal tools support the creation and management of:

- clothing  
- cosmetics  
- accessories  
- brand swag  
- user model rigs  
- preset-only content  
- content publishing  
- asset validation  

These tools are **content-facing**, not engineering-facing.  
They complement the `/planning/dev-tools` folder, which focuses on engineering workflows.

---

# 2. Documents in This Folder

| Document | Purpose |
|---------|---------|
| **BRAND_SWAG_PIPELINE_TOOL_PLANNING.md** | Tool for creating and validating branded cosmetics |
| **CLOTHING_DESIGNER_TOOL_PLANNING.md** | Tool for designing clothing and outfits |
| **CONTENT_PUBLISHING_PIPELINE_PLANNING.md** | Tool for staging, scheduling, and publishing content |
| **COSMETIC_CREATION_SUITE_PLANNING.md** | Unified tool for creating all cosmetic types |
| **INTERNAL_ASSET_VALIDATOR_TOOL_PLANNING.md** | Automated validation for safety, performance, and compliance |
| **PRESET_CONTENT_BUILDER_TOOL_PLANNING.md** | Tool for creating preset-only, Zero Moderation-safe content |
| **USER_MODEL_RIGGING_TOOL_PLANNING.md** | Tool for validating rigs, weights, and accessory fit |

---

# 3. Guiding Principles

Internal tools must:

- support **safe, deterministic workflows**  
- enforce **child-safety** and **Zero Moderation** rules  
- reduce manual asset preparation  
- empower non-engineering teams  
- integrate with the content publishing pipeline  
- ensure consistent visual and technical quality  

---

# 4. Relationship to Other Planning Areas

Internal tools interact with:

### `/planning/dev-tools`
- dev dashboards  
- debugging tools  
- experimentation frameworks  
- admin tools  

### `/planning/core/security_standards`
- asset validation rules  
- publishing safety rules  
- Zero Moderation enforcement  

### `/platform/core/security`
- platform-wide safety doctrine  

---

# 5. Intended Audience

- internal artists  
- internal designers  
- brand teams  
- content managers  
- internal creators  
- QA  
- publishing operators  
- engineering leads (for integration awareness)

---

# 6. Success Criteria

This folder is successful when:

- internal teams can create content without engineering support  
- tools are clearly defined and scoped  
- workflows are deterministic and safe  
- all content passes validation before publishing  
- documentation is consistent and easy to navigate  

