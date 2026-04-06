# AI Investigator Sandbox Planning

---

## 🎯 Purpose
Define the isolated sandbox environment used by AI Investigator to safely replay failures, test potential fixes, validate hypotheses, and generate Issue Intake items — without ever touching production systems.

---

# 1. Goals
- Provide a safe environment for AI experimentation  
- Allow deterministic replay of failures  
- Validate fixes before human review  
- Prevent any production impact  
- Support Dev Dashboard and Issue Intake  

---

# 2. Personas
- **AI Investigator:** Needs a safe place to test fixes  
- **Engineer:** Needs validated results before reviewing  
- **Platform:** Needs strict isolation and safety  

---

# 3. User Stories
- *As AI Investigator, I want to replay failures safely.*  
- *As an engineer, I want fixes validated before I review them.*  
- *As the platform, I want zero risk to production.*  

---

# 4. Core Capabilities
- Failure replay  
- State reconstruction  
- Fix simulation  
- Validation engine  
- Snapshot isolation  
- Log and trace capture  
- Integration with Issue Intake  

---

# 5. Workflows

### **5.1 Replay Workflow**
1. AI Investigator receives logs, traces, and signatures  
2. Sandbox reconstructs failure state  
3. Sandbox replays the issue deterministically  

### **5.2 Fix Testing Workflow**
1. AI proposes potential fix  
2. Sandbox applies fix to isolated state  
3. Sandbox replays scenario  
4. Sandbox records results  
5. AI generates Issue Intake item  

### **5.3 Engineer Review Workflow**
1. Dev Dashboard displays sandbox results  
2. Engineer reviews fix and validation  
3. Engineer approves or modifies fix  

---

# 6. Rules & Constraints
- Sandbox cannot access production data  
- Sandbox cannot deploy changes  
- Sandbox must be ephemeral  
- Sandbox must be deterministic  
- All sandbox actions logged  

---

# 7. Deep Dive

### **7.1 Sandbox Architecture**
- Isolated compute environment  
- Deterministic state loader  
- Replay engine  
- Fix simulation engine  
- Validation engine  
- Log/trace recorder  

### **7.2 Sandbox Inputs**
- Logs  
- Error signatures  
- Stack traces  
- Service metadata  
- Config snapshots  

### **7.3 Sandbox Outputs**
- Replay logs  
- Fix validation results  
- Confidence scores  
- Issue Intake attachments  

---

# 8. Success Criteria
- Safe, reproducible testing  
- High‑quality Issue Intake items  
- Engineers trust AI outputs  
- Zero production risk  
