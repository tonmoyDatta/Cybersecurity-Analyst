# Cybersecurity Incident Report

## Section 1: Identify the Type of Attack
A potential cause of the website's connection timeout error is a **Denial of Service (DoS) attack**. The logs indicate that the web server becomes unresponsive when flooded with **SYN packet requests**, pointing to a **SYN flooding attack**, a common type of DoS attack.

---

## Section 2: Explanation of the Attack's Impact on the Website
When visitors attempt to connect to the web server, a **three-way handshake** is initiated using the **TCP protocol**. This process involves the following steps:
1. The source sends a **SYN packet** to the destination, requesting a connection.
2. The destination responds with a **SYN-ACK packet**, accepting the connection request and reserving resources for the source.
3. The source sends a final **ACK packet** to the destination, confirming the connection.

During a **SYN flood attack**, a malicious actor sends a large volume of **SYN packets** simultaneously, overwhelming the server's resources reserved for connections. As a result, the server cannot allocate resources for legitimate TCP connection requests.

The logs show that the web server has been overwhelmed and is unable to process SYN requests from visitors. This prevents the server from establishing new connections, causing visitors to receive a **connection timeout error message**.

---

## Section 3: Analysis of Wireshark Logs
The Wireshark log file reveals the following key observations:
- A high volume of **SYN packets** originating from an unfamiliar IP address (`203.0.113.0`).
- The server responds with **SYN-ACK packets** but is unable to complete the three-way handshake due to the overwhelming number of requests.
- Legitimate connection attempts from known IP addresses (e.g., `198.51.100.x`) are interrupted or fail due to the server's inability to allocate resources.
- The server eventually sends **RST (reset) packets** to terminate incomplete connections, further indicating resource exhaustion.

---

## Section 4: Immediate Actions Taken
1. **Took the server offline temporarily** to allow it to recover and return to normal operation.
2. **Configured the firewall** to block the suspicious IP address (`203.0.113.0`) sending the abnormal SYN requests.
3. Noted that IP blocking is a temporary solution, as attackers can spoof IP addresses to bypass such measures.

---

## Section 5: Recommendations for Prevention
To mitigate future attacks, the following measures are recommended:
1. Implement **rate limiting** on SYN requests to prevent overwhelming the server.
2. Configure **SYN cookies** to handle large volumes of SYN requests without reserving resources.
3. Deploy an **Intrusion Detection System (IDS)** or **Intrusion Prevention System (IPS)** to detect and block malicious traffic in real-time.
4. Regularly update and patch the server and firewall to address vulnerabilities.
5. Consider using a **Content Delivery Network (CDN)** or **DDoS protection service** to absorb and filter malicious traffic.

---

## Conclusion
The incident was caused by a **SYN flood attack**, which overwhelmed the web server's resources and prevented legitimate users from accessing the website. Immediate actions were taken to mitigate the attack, but long-term solutions are necessary to prevent recurrence. Further investigation and implementation of advanced security measures are recommended to safeguard the web server against future attacks.
