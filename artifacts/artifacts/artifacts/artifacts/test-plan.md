
# Test Plan for CUI Sensitivity Label & DLP Policies

This test plan validates that sensitivity labels and DLP rules for **Controlled Unclassified Information (CUI)** behave as expected across Microsoft 365 workloads.

---

## Test Case 1 — External Email Block
**Objective:** Ensure CUI cannot be emailed externally  
**Action:**  
Send a CUI‑labeled file to a Gmail/Outlook.com address  

**Expected Result:**  
- Email is **blocked**  
- Override requires justification  
- DLP incident is generated  
- Visible in Activity Explorer

---

## Test Case 2 — External File Sharing Block (SharePoint/OneDrive)
**Objective:** Prevent external sharing of CUI files  
**Action:**  
Attempt to share a CUI‑labeled document with an external user  

**Expected Result:**  
- Sharing is **blocked**  
- Policy tip appears  
- Event logged in Activity Explorer

---

## Test Case 3 — USB Copy Block (Endpoint)
**Objective:** Ensure endpoint rules block USB exfiltration  
**Action:**  
Try copying a CUI‑labeled file to a removable USB drive  

**Expected Result:**  
- Copy action is **blocked**  
- High‑severity alert sent to compliance  
- Event logged as Endpoint DLP alert

---

## Test Case 4 — Printing Block (Endpoint)
**Objective:** Prevent printing of CUI content  
**Action:**  
Attempt to print a CUI‑labeled document  

**Expected Result:**  
- Printing is blocked OR monitored with alert  
- Event appears in Activity Explorer or Endpoint alerts

---

## Purpose
These tests validate that labeling and DLP configuration satisfies key compliance controls:

- **CMMC Level 2**
  - 3.1.3 — Control access to CUI  
  - 3.8.9 — Protect CUI during transmission

- **NIST 800‑171**
  - 3.13.11 — Cryptographic protections  
  - 3.3.x — Audit and accountability  

