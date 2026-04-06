# SYSTEM_LIFECYCLE_MANAGEMENT

---

## 🎯 Purpose
Define how systems are introduced, evolved, and retired across EndlessGames in a controlled, documented way.

---

## 🧱 Lifecycle Stages

1. **Concept:** Idea exists, not yet planned.
2. **Planned:** Planning doc created and aligned with doctrine.
3. **Implemented:** System built and deployed.
4. **Operational:** System is live and maintained.
5. **Evolving:** System receives structured improvements.
6. **Deprecated:** System is being phased out.
7. **Retired:** System is fully removed or replaced.

---

## 📏 Lifecycle Rules

- No system skips the planning stage.
- All systems must reference PLATFORM_DOCTRINE_OVERVIEW.
- All systems must declare owners and dependencies.
- Deprecation requires a migration plan and updated docs.

---

## 🔄 Migration Workflow

1. Identify successor system (if any).
2. Document impact and dependencies.
3. Update `PLATFORM_DEPENDENCY_MAP` and relevant planning docs.
4. Implement migration logic and communication.
5. Retire old system and mark docs as legacy.

---

## 🧪 Versioning

- Major changes → update planning docs and version.
- Minor changes → update affected sections and dependency notes.
- Experimental / future systems → live in `/future` until stabilized.
