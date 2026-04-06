# Copilot Security Index

## Purpose
Defines how GitHub Copilot should route security‑related prompts to the correct document.

---

# Routing Table

## UI Security
Use these when prompts involve:
- XSS  
- CSRF  
- DOM safety  
- rendering safety  
- iframe security  
- third‑party embeds  

Docs:
- frontend_security_best_practices.md  
- ui_input_sanitization_guidelines.md  
- ui_rendering_safety_rules.md  
- ui_third_party_content_safety.md  
- ui_iframe_and_embedding_security.md  

---

## Backend Security
Use these when prompts involve:
- APIs  
- authentication  
- sessions  
- backend validation  
- rate limiting  
- service‑to‑service trust  
- backend logging  
- backend secrets  
- backend configuration  

Docs:
- backend_security_principles.md  
- service_to_service_security.md  
- backend_rate_limiting_and_abuse_prevention.md  
- backend_input_validation_and_sanitization.md  
- backend_error_handling_and_information_leakage.md  
- backend_logging_and_audit_security.md  
- backend_secrets_and_key_rotation.md  
- backend_configuration_security.md  
- api_security_best_practices.md  
- authentication_and_session_best_practices.md  
- dependency_and_supply_chain_security.md  
- secrets_management_best_practices.md  
- penetration_test_preparation.md  
- secure_coding_principles.md  

---

## Data Security
Use these when prompts involve:
- encryption  
- access control  
- classification  
- retention  
- deletion  
- backups  
- integrity  
- governance  

Docs:
- data_security_principles.md  
- data_encryption_at_rest_and_in_transit.md  
- data_access_control_and_permissions.md  
- data_classification_and_handling.md  
- data_retention_and_deletion_security.md  
- data_audit_and_governance.md  
- data_backup_and_recovery_security.md  
- data_integrity_and_tamper_prevention.md  

---

# Summary
Copilot must always route prompts to the correct pillar before generating code or documentation.
