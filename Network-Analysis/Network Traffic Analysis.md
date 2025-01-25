# Cybersecurity Incident Report: Network Traffic Analysis

# Log Data 

13:24:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35084+ A? yummyrecipesforme.com. (24)
13:24:36.098564 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 udp port 53 unreachable length 254

13:26:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35084+ A? yummyrecipesforme.com. (24)
13:27:15.934126 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 udp port 53 unreachable length 320

13:28:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35084+ A? yummyrecipesforme.com. (24)
13:28:50.022967 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 udp port 53 unreachable length 150


---



## Part 1: Provide a summary of the problem found in the DNS and ICMP traffic log

Answer: Based on the network analysis, it was observed that the UDP protocol attempted to communicate with the DNS server on port 53 to retrieve the IP address for the domain name **yummyrecipesforme.com**. However, the ICMP protocol responded with an error message, "udp port 53 unreachable," indicating issues with contacting the DNS server. The outgoing UDP message is shown in the first two lines of each log event, while the ICMP error response appears in the third and fourth lines, highlighting port 53 as the cause.

Since port 53 is associated with DNS traffic, this suggests a problem with the DNS server. Further evidence lies in the flags within the UDP message and the “A?” symbol, which point to issues performing DNS protocol operations. Therefore, it is highly likely that the DNS server is unresponsive.

---

## Part 2: Explain your analysis of the data and provide at least one cause of the incident

Answer: The incident was reported today at 1:24 p.m. when customers informed the organization that they encountered the message “destination port unreachable” while attempting to access the website **yummyrecipesforme.com**. The cybersecurity team, responsible for IT support for the client organization, is actively investigating the issue to restore website access.

As part of the investigation, packet sniffing tests were performed using **tcpdump**, and the logs revealed that DNS port 53 was unreachable. The next steps involve determining whether the DNS server is offline or if traffic to port 53 is being blocked by a firewall. Potential causes for the DNS server being down include a successful Denial of Service (DoS) attack or a misconfiguration.
