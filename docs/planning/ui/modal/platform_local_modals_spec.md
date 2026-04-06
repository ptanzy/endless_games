# EndlessOS — Platform Local Modal Specification

## Purpose
Platform‑local modals provide lightweight, platform‑specific controls without overwhelming the global settings system.  
These modals allow each EndlessOS platform (Games, Tube, Music, Books, Events) to expose quick, contextual settings while maintaining:

- Deterministic behavior  
- Neutral visual language  
- Cinematic calm  
- Strict safe zone compliance  
- Zero layout shift  
- No platform identity leakage into system UI  

Platform‑local modals are **not** global modals.  
They are **scoped** to the platform page and must never override system‑level modal rules.

---

# Core Philosophy

## 1. Platform‑Local, Not System‑Level
Platform‑local modals:
- Are triggered from within a platform page  
- Apply only to that platform  
- Never affect global settings  
- Never use platform accent colors  
- Never use platform backgrounds  

They must remain **neutral**, even though they are platform‑specific.

---

## 2. Lightweight and Fast
Platform‑local modals must be:
- Small  
- Quick to open  
- Quick to close  
- Minimal in content  
- Focused on immediate actions  

They are not full settings pages.  
They are **micro‑settings surfaces**.

---

## 3. Deterministic and Non‑Adaptive
Platform‑local modals must:
- Always appear centered  
- Always use the same size rules  
- Never resize dynamically  
- Never shift layout  
- Never adapt based on content  

Consistency is mandatory.

---

## 4. No Platform Identity
Even though these modals belong to a platform, they must **never** use:
- Platform accent colors  
- Platform backgrounds  
- Platform typography  

They must remain visually neutral to avoid UI fragmentation.

---

# Modal Structure

Platform‑local modals follow a compact structure:

