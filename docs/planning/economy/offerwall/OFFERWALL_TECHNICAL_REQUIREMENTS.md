# OFFERWALL_TECHNICAL_REQUIREMENTS

---

## 🎯 Purpose

Define the technical requirements for integrating offerwall vendors into EndlessGames.

---

# 1. Goals

- Ensure deterministic reward attribution  
- Support multiple vendors  
- Maintain strong fraud prevention  
- Provide a unified callback system  

---

# 2. Callback Requirements

- HTTPS only  
- Signed callbacks  
- Timestamped  
- Nonce included  
- Vendor IP allowlist  

---

# 3. Required Data Fields

- User ID  
- Offer ID  
- Reward amount  
- Transaction ID  
- Timestamp  
- Signature  

---

# 4. Fraud Prevention

- Device fingerprinting  
- IP checks  
- Duplicate prevention  
- Velocity checks  
- Vendor fraud filters  

---

# 5. Offerwall Embedding

- WebView or iframe  
- Vendor SDK (if required)  
- Unified wrapper  

---

# 6. Deep Dive

### **6.1 Reward Attribution Engine**
- Deduplication  
- Idempotent callbacks  
- Creator attribution (future)  

### **6.2 Analytics Events**
- Offer viewed  
- Offer clicked  
- Offer started  
- Offer completed  
- Reward delivered  

---

# 7. Success Criteria

- Zero reward errors  
- Low fraud  
- High reliability  
