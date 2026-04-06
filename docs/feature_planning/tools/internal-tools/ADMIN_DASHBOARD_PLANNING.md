# Internal Admin Dashboard Planning

---

## 🎯 Purpose
Provide EndlessGames operational staff with a safe, internal‑only dashboard for managing creators, reviewing presets, overseeing events, and handling platform‑level administrative workflows — without exposing any engineering or debugging tools.

---

# 1. Goals
- Support preset review and approval  
- Support creator verification and management  
- Support event and season scheduling  
- Provide operational oversight  
- Maintain strict access control  

---

# 2. Personas
- **Admin:** Manages presets, creators, and events  
- **Safety Team:** Oversees flagged content and compliance  
- **Platform Ops:** Manages seasonal and platform‑wide configurations  

---

# 3. User Stories
- *As an admin, I want to review and approve preset packs.*  
- *As an admin, I want to verify creators.*  
- *As platform ops, I want to schedule seasonal events.*  
- *As the safety team, I want to see flagged presets or creators.*  

---

# 4. Core Capabilities
- Preset Review Module  
- Creator Verification Module  
- Creator Tier Management  
- Event & Season Scheduler  
- Clan Oversight (non‑technical)  
- Media System Health Summaries (non‑technical)  
- Access Control & Audit Logs  

---

# 5. Workflows

### **5.1 Preset Review Workflow**
1. Preset submitted  
2. Automated checks run  
3. Admin reviews  
4. Approve or request changes  
5. Pack enters catalog  

### **5.2 Creator Verification Workflow**
1. Creator applies  
2. Admin reviews profile  
3. Approve or deny  
4. Creator tier updated  

### **5.3 Event Scheduling Workflow**
1. Admin selects event template  
2. Configures dates and rewards  
3. Publishes event  
4. System propagates event to all surfaces  

---

# 6. Rules & Constraints
- No access to logs, traces, or debugging tools  
- No ability to modify player data  
- No engineering‑level visibility  
- All actions logged  
- Internal‑only  

---

# 7. Deep Dive

### **7.1 Dashboard Modules**
- Preset Review  
- Creator Management  
- Event Scheduler  
- Clan Oversight  
- Media System Health (summary only)  

### **7.2 Security Requirements**
- MFA  
- RBAC  
- Audit logging  
- Least‑privilege access  

---

# 8. Success Criteria
- Operational staff can manage presets, creators, and events  
- No engineering tools exposed  
- Zero moderation risk  
- Clean separation from Dev Dashboard  
