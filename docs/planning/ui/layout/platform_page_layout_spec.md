# EndlessOS — Platform Page Layout Specification

## Purpose
Platform pages represent the core content surfaces of EndlessOS:  
**Games, Tube, Music, Books, and Events.**

This specification defines:
- Structural layout  
- Page composition  
- Platform identity integration  
- Grid behavior  
- Section rules  
- Interaction behavior  
- Tooltip usage  
- Anti‑patterns  

Platform pages inherit from:
- layout_design_doctrine.md  
- layout_system_overview.md  
- safe_zone_rules.md  
- tooltip_spec.md  

They must remain structurally identical across all platforms, with only identity (accent + background) varying.

---

# Platform Page Philosophy

Platform pages must feel:
- Cinematic  
- Calm  
- Content‑first  
- Identity‑rich but structurally consistent  

They are the **primary browsing surfaces** for each content type and must support:
- High‑density content grids  
- Clear hierarchy  
- Predictable navigation  
- Optional hover tooltips  
- Deterministic layout behavior  

Platform identity is expressed through:
- Accent color  
- Background  
- Display typography (optional)  

Platform identity must **never** affect:
- Grid structure  
- Spacing  
- Safe zones  
- Component behavior  

---

# Page Structure

Platform pages follow a strict, deterministic structure:

