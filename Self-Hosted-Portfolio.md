# Vulnerability Assessment Report  
**10 December 2024**  

---

## System Description  
The server hardware consists of a powerful CPU processor and 128GB of memory. It runs on the latest version of the Linux operating system and hosts a MySQL database management system. It is configured with a stable network connection using IPv4 addresses and interacts with other servers on the network. Security measures include SSL/TLS encrypted connections.  

## Scope  
The scope of this vulnerability assessment relates to the current access controls of the system. The assessment will cover a period of three months, from January 2025 to March 2025. NIST SP 800-30 Rev. 1 is used to guide the risk analysis of the information system.  

## Purpose  
The database server is a critical centralized system that stores and manages large amounts of customer, campaign, and analytic data, essential for tracking performance and personalizing marketing efforts. The business relies on a MySQL database server to conduct online services, with remote workers accessing it from different locations. Ensuring its security is paramount to protect sensitive information and prevent disruption, as any downtime or compromise would significantly impact business operations.  

## Risk Assessment  

| Threat Source             | Threat Event                                     | Likelihood | Severity | Risk |
|---------------------------|-------------------------------------------------|------------|----------|------|
| Hacker/ Malicious software | Obtain sensitive information via exfiltration   | 3          | 3        | 9    |
| Employee                  | They might intentionally steal data and damage business equipment. | 2          | 3        | 6    |
| Customer                  | Alter/Delete critical information               | 1          | 3        | 3    |

## Approach  
The evaluation of risks focused on the business's data storage and management practices. This included identifying potential threat sources and events while analyzing the likelihood of a security breach due to the open access permissions of the information system. The severity of these risks was measured against their potential impact on daily operations, ensuring a balanced consideration of security and functionality.  

## Remediation Strategy  
To address identified risks, robust measures are prioritized based on severity. For high-risk threats like hackers (Risk: 9), deploy firewalls, IDS/IPS, encryption (AES/TLS), and regular vulnerability assessments. Medium-risk employee threats (Risk: 6) are mitigated through role-based access controls (RBAC), activity monitoring, cybersecurity training, and clear NDAs. Low-risk customer threats (Risk: 3) are managed with multi-factor authentication (MFA), restricted user privileges, activity logging, and regular data backups to ensure quick recovery. These actions collectively safeguard the system and minimize disruptions to operations.  

