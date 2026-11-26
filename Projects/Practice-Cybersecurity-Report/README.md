# Activity: DNS Incident Report

- **Course:** Google Cybersecurity Certificate - Course 3 (Connect and Protect: Networks and Network Security)
- **Platform:** Google Skills
- **Category:** Incident Response and Network Traffic Analysis
- **Tools Used:** `tcpdump`, DNS over UDP, ICMP
- **Materials reviewed:** Incident report template, completed analysis, and course exemplar

## Objective

Analyze a website availability issue using DNS and ICMP log evidence, explain how the failure affects users, and identify likely causes for further investigation.

## Scenario

Users report that they cannot reach a company website. The investigation captures network traffic between a client and its DNS server to determine why the browser cannot resolve the website's domain name.

## Method

1. Reviewed the incident report scenario and the DNS/ICMP traffic findings.
2. Identified the protocol and destination port used for the DNS queries.
3. Compared the repeated DNS requests with the corresponding ICMP error responses.
4. Documented the effect on name resolution and listed plausible causes without treating an unconfirmed cause as established fact.

## Findings

| Observation | Evidence | Significance |
|---|---|---|
| DNS queries use UDP port 53 | The client sends DNS requests to the configured resolver at `203.0.113.2` on port 53. | DNS resolution is required for the browser to obtain the website's IP address. |
| The requests receive an ICMP error | The capture shows repeated ICMP responses reporting `udp port 53 unreachable`. | The client cannot complete the DNS lookup, so the browser cannot proceed to connect to the website. |
| The underlying cause is not confirmed by the capture alone | The symptoms could be caused by an unavailable DNS service or a firewall rule blocking DNS traffic. A denial-of-service condition is another possibility to investigate. | Additional server health, firewall, and security evidence is needed before attributing the incident to an attack. |

## Response and Next Steps

1. Check DNS service health and resolver availability.
2. Review firewall and network changes affecting UDP port 53.
3. Compare resolver and network logs with the incident timeline; investigate denial-of-service indicators if other evidence supports that possibility.
4. Restore DNS service or connectivity, then verify successful resolution and website access.
5. Document the cause, impact, response actions, and any preventive changes.

## Result

The captured traffic indicates a DNS resolution failure: UDP queries to port 53 are met with ICMP port-unreachable errors. This explains why the website cannot be reached, but further investigation is required to determine whether the cause is a service outage, network configuration, or malicious activity.

## Key Takeaway

Protocol-level evidence can isolate where a connection fails. Correlating DNS and ICMP traffic with system and firewall records helps distinguish symptoms from root cause.

## Supporting Materials

- [Incident scenario reference](./Scenario.png)
- [Incident report template](./Cybersecurity-incident-report-network-traffic-analysis.pdf)
- [Completed DNS traffic analysis](./My-answers-in-Cybersecurity-incident-report-network-traffic-analysis.pdf)
- [Course reference report](./The-Exemplar-Explained-Cybersecurity-Incident-Report-Network-Traffic-Analysis.pdf)
