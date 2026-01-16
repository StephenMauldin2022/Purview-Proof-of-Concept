
# Microsoft Purview DLP Policy — CUI Protection

This DLP policy enforces controls to prevent unauthorized transmission or handling of
**Controlled Unclassified Information (CUI)** in Microsoft 365.

---

##  Policy Name
**CUI Data Exfiltration Protection**

---

##  Workloads Covered
- Exchange Online  
- SharePoint Online  
- OneDrive for Business  
- Teams (files, chats)  
- Endpoint DLP (conceptual)

---

##  Rule 1 — Block External Sharing of CUI
**Condition:**  
- Content contains sensitivity label `CUI`

**Actions:**  
- Block sharing with external domains  
- Allow override with business justification  
- Display policy tip: **“CUI cannot be shared externally.”**

---

## Rule 2 — Endpoint USB & Print Protection
**Condition:**  
- File is labeled `CUI`

**Actions:**  
- Block copying to USB/removable drives  
- Block printing of CUI documents  
- Generate high-severity DLP alert

---

## Rule 3 — Email Exfiltration Control
**Condition:**  
- Email contains CUI-labeled file or CUI text content  
- Recipient is external

**Actions:**  
- Block sending  
- Log event in Activity Explorer  
- Send DLP incident report to compliance team

---

## Compliance Mapping
- **CMMC Level 2:**  
  - 3.1.3 — Control access to CUI  
  - 3.8.9 — Protect CUI during transmission  
- **NIST 800-171:**  
  - 3.13.11 — Cryptographic protections  
  - 3.3.x — Audit and incident reporting

---

## Purpose
This DLP policy creates layered controls across email, file storage, and endpoints to ensure CUI is never exfiltrated or mishandled, supporting CMMC and NIST compliance requirements.

