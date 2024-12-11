# NIST SP 800-30 Rev. 1

## Guide to Assessing Risk

**NIST SP 800-30** is a publication that provides guidance on performing risk assessments. It outlines strategies for identifying, analyzing, and remediating risks. Organizations use NIST SP 800-30 to understand the likelihood and severity of risks, aiding in resource allocation, control implementation, and prioritization of remediation efforts.

This guide is adapted from **NIST SP 800-30 Rev. 1**, where "Rev. 1" signifies its first updated version. NIST revises documents periodically to reflect new information, advancements in technology, regulatory changes, or user feedback.

> **Note**: For more details, visit NIST's [Computer Security Resources Center](https://csrc.nist.gov).

---

## Threat Sources

NIST SP 800-30 categorizes **threat sources** as entities or circumstances that negatively impact an organization's information systems. These sources help identify and assess risks by considering the intent and capabilities of internal and external threats.

### Common Threat Sources and Examples

| **Type**            | **Examples**                                                                                       | **Description**                                                                                                                                      |
|----------------------|---------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Standard user        | ● Employee<br>● Customer                                                                         | Threats from users who might accidentally or maliciously misuse access, potentially impacting business operations.                                    |
| Privileged user      | ● System administrator                                                                          | Higher-privileged users whose actions, intentional or accidental, could severely impact systems.                                                     |
| Group                | ● Competitor<br>● Supplier<br>● Business partner<br>● Nation state                              | External entities or groups with potential motives to exploit systems, including industrial espionage or sabotage.                                   |
| Outsider             | ● Hacker<br>● Hacktivist<br>● Advanced Persistent Threat (APT)                                  | Individuals or groups who may exploit vulnerabilities to steal data, disrupt operations, or cause reputational harm.                                 |
| Hardware             | ● Storage<br>● Processing<br>● Communications                                                   | Non-human threats like aging equipment or hardware failures that could disrupt operations.                                                           |
| Software             | ● Operating system(s)<br>● Networking<br>● Malicious software                                   | Failures or vulnerabilities in software, including malware infections, that can impact system availability and integrity.                            |
| Operational environment | ● Temperature controls<br>● Humidity controls<br>● Faulty power supplies                   | Environmental issues, such as improper controls or resource failures, that indirectly impact system operations.                                       |
| Natural hazards      | ● Power outages<br>● Extreme weather events                                                     | Natural events that could damage physical infrastructure or disrupt business continuity.                                                             |

---

## Threat Events

**Threat events** are actual instances where a threat source exploits a vulnerability, causing harm. Understanding these events aids in identifying effective controls and countermeasures.

### Examples of Threat Events

| **Examples**                                      | **Description**                                                                                             |
|---------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| Perform reconnaissance and surveillance          | Threat source examines vulnerabilities using tools like scanning or physical observation.                   |
| Obtain sensitive information via exfiltration    | Threat source installs malicious software to locate and extract sensitive data.                             |
| Alter/Delete critical information                | Threat source modifies or removes vital business data, disrupting operations.                               |
| Craft counterfeit certificates                   | Threat source compromises certificate authorities to create seemingly legitimate connections.                |
| Install persistent and targeted network sniffers | Threat source deploys software to capture network traffic over time.                                        |
| Conduct Denial of Service (DoS) attacks          | Excessive automated requests overwhelm system resources, causing outages.                                   |
| Disrupt mission-critical operations              | Threat source corrupts data or systems, preventing essential business functions.                            |
| Obfuscate future attacks                         | Actions to bypass intrusion detection or audit trails to conceal malicious activity.                        |
| Conduct "man-in-the-middle" attacks              | Threat source intercepts and manipulates communication between systems.                                     |

---

## Likelihood of a Threat Event

Likelihood evaluates the probability of a threat event based on evidence, past experience, and expert judgment. Consider the intent and capabilities of the threat source alongside potential events.

| **Qualitative Values** | **Quantitative Values** | **Description**                                                                                              |
|-------------------------|-------------------------|--------------------------------------------------------------------------------------------------------------|
| High                   | 3                       | Threat source is almost certain to initiate an event with severe or catastrophic effects.                   |
| Moderate               | 2                       | Threat source is somewhat likely to initiate an event, causing significant disruption.                      |
| Low                    | 1                       | Threat source is unlikely to initiate an event with minor or negligible effects.                            |

---

## Severity of a Threat Event

Severity measures the impact of a threat event on business operations. It considers whether the event disrupts critical processes or causes minor inconveniences.

| **Qualitative Values** | **Quantitative Values** | **Description**                                                                                              |
|-------------------------|-------------------------|--------------------------------------------------------------------------------------------------------------|
| High                   | 3                       | Event causes multiple severe or catastrophic effects on business operations.                                |
| Moderate               | 2                       | Event significantly reduces functionality of business processes and assets.                                |
| Low                    | 1                       | Event has minor or negligible effects on operations and assets.                                             |

