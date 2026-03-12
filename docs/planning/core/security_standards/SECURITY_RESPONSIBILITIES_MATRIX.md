# SECURITY_RESPONSIBILITIES_MATRIX

---

## 🎯 Purpose

This matrix defines **who owns what** across the EndlessGames security ecosystem.  
It ensures clarity, accountability, and predictable escalation paths.

---

# 1. ROLES

| Role | Description |
|------|-------------|
| **Security Lead** | Owns platform security doctrine and audits |
| **Backend Lead** | Owns backend service security implementation |
| **Frontend Lead** | Owns frontend security implementation |
| **Infrastructure Lead** | Owns cloud, network, and container security |
| **DevOps Lead** | Owns CI/CD and deployment security |
| **Data Governance Lead** | Owns data lifecycle and retention rules |
| **Pen Test Coordinator** | Manages internal and external pen tests |
| **On‑Call Engineer** | Responds to incidents and triggers rollbacks |

---

# 2. RESPONSIBILITY MATRIX (RACI)

### **Platform Security Doctrine**

| Task | Security Lead | Backend Lead | Frontend Lead | Infra Lead |
|------|---------------|--------------|---------------|------------|
| Maintain security standards | **R** | C | C | C |
| Approve changes | **A** | C | C | C |
| Implement changes | C | **R** | **R** | **R** |

---

### **Penetration Testing**

| Task | Security Lead | Pen Test Coordinator | Engineering Leads |
|------|---------------|----------------------|-------------------|
| Schedule tests | C | **R** | C |
| Execute tests | C | **A/R** | C |
| Remediate findings | C | C | **R** |

---

### **Incident Response**

| Task | Security Lead | On‑Call Engineer | Infra Lead |
|------|---------------|------------------|------------|
| Declare incident | **A** | R | C |
| Mitigate impact | C | **R** | **R** |
| Trigger rollback | C | **R** | C |
| Post‑incident review | **R** | C | C |

---

### **Data Lifecycle**

| Task | Data Governance Lead | Security Lead | Engineering Leads |
|------|-----------------------|---------------|-------------------|
| Define retention rules | **R** | C | C |
| Implement deletion workflows | C | C | **R** |
| Audit compliance | **A/R** | C | C |

---

# 3. SUCCESS CRITERIA

This matrix is successful when:

- responsibilities are clear  
- escalations are predictable  
- incidents are resolved quickly  
- audits show consistent ownership  
- security improvements have clear owners  

