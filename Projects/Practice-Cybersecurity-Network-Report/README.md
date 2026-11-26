# Activity: TCP Network Traffic Analysis

- **Course:** Google Cybersecurity Certificate - Course 3 (Connect and Protect: Networks and Network Security)
- **Platform:** Google Skills
- **Category:** Network Analysis and Incident Response
- **Tools Used:** Wireshark, TCP/HTTP log review
- **Materials reviewed:** TCP log, color-coded analysis, and completed incident report

## Objective

Review TCP/HTTP traffic to distinguish normal connections from repeated connection attempts, identify how the traffic affects legitimate users, and document a likely denial-of-service pattern.

## Scenario

Users report timeouts while trying to access a website. The exercise provides a packet log and a color-coded copy that distinguishes normal handshakes, suspected attack traffic, and legitimate connections that fail during the incident.

## Method

1. Reviewed the TCP log and the color-coded packet sequence.
2. Identified the normal TCP three-way handshake: SYN, SYN-ACK, and ACK.
3. Compared ordinary client traffic with repeated SYN packets that do not complete normal handshakes.
4. Looked for service-impact indicators, including resets and an HTTP gateway timeout.
5. Compared the packet evidence with the incident report to describe the likely attack pattern.

## Findings

| Observation | Evidence | Significance |
|---|---|---|
| Normal clients can complete connections | The log includes completed handshakes followed by HTTP requests and `200 OK` responses. | This establishes a baseline for expected traffic. |
| One source repeatedly sends SYN requests | Repeated connection attempts target the web service without consistently completing the handshake. | The pattern is consistent with a TCP SYN flood and may consume server connection resources. |
| Some legitimate requests fail | The log includes reset connections and an HTTP `504 Gateway Time-out` response during the repeated SYN activity. | The observed pattern coincides with reduced availability for legitimate users. |

## Recommendations

1. Correlate packet evidence with server, load-balancer, and firewall metrics to confirm impact and scope.
2. Apply provider-supported denial-of-service protections, connection-rate controls, and appropriate TCP backlog protections.
3. Preserve relevant logs and timestamps, and monitor whether legitimate connection success returns after mitigation.
4. Document the confirmed root cause and recovery actions; do not attribute activity to a specific person from an IP address alone.

## Result

The repeated incomplete SYN activity and concurrent connection failures are consistent with a SYN flood causing service disruption. The logs support the suspected pattern, while attribution and final root cause require corroborating evidence.

## Key Takeaway

Comparing a normal handshake with repeated incomplete connections helps identify availability issues. Packet captures are most useful when interpreted alongside server-side telemetry and the broader incident timeline.

## Supporting Materials

- [TCP/HTTP log](./Wireshark-TCP-HTTP-log-TCP-log.pdf)
- [Color-coded TCP log](./Wireshark-TCP-HTTP-log-Color-coded-TCP-log.pdf)
- [Completed incident report](./My-answer-Cybersecurity-incident-report.pdf)
