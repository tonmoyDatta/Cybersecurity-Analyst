# Incident Report Analysis

## Summary
This morning, an intern reported being unable to log in to her internal network account. Access logs revealed her account was actively accessing records in the customer database despite being locked out. The intern received a phishing email directing her to an external website to log in with her credentials, which we believe was the attack vector. Several customer records were found missing or altered, indicating unauthorized access, data deletion, and manipulation.

---

## Identify
- **Root Cause**: A malicious actor obtained the intern’s login credentials via a phishing email.  
- **Impact**: Unauthorized access to the customer database, deletion/modification of records.  
- **Gaps Identified**:  
  - Lack of multi-factor authentication (MFA).  
  - Insufficient employee training on phishing threats.  
  - Weak monitoring of suspicious login activity.  

---

## Protect
**Immediate Actions**:  
- Enforced **multi-factor authentication (MFA)** for all internal accounts.  
- Limited login attempts to **3 tries** before account lockout.  
- Initiated **mandatory security training** for employees and interns on credential protection.  

**Long-Term Measures**:  
- Deployed a **new firewall configuration** with stricter traffic filtering.  
- Invested in an **intrusion prevention system (IPS)** to block malicious activities.  

---

## Detect
**Enhanced Monitoring Tools**:  
- **Firewall Logging Tool**: Tracks all incoming/outgoing traffic patterns.  
- **Intrusion Detection System (IDS)**: Monitors network traffic for anomalies and unauthorized access attempts.  

---

## Respond
**Immediate Steps**:  
- Disabled the compromised intern account.  
- Conducted **emergency training sessions** for staff to prevent credential sharing and phishing risks.  

**Communication**:  
- Notified upper management of the breach.  
- Customers will be informed via mail about the data exposure.  
- Law enforcement and regulatory bodies will be engaged as required by local laws.  

---

## Recover
**Data Restoration**:  
- Restoring the customer database from **last night’s full backup**.  
- Staff must re-enter any customer data modified/added after the backup was taken.  

**Post-Incident Actions**:  
- Scheduled **daily incremental backups** to minimize data loss in future incidents.  

---

## Reflections/Notes
- **Phishing simulations** will be added to future training programs.  
- Review backup protocols to ensure faster recovery times.  
