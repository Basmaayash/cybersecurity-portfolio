# 🛡️ Cybersecurity Incident Report – SYN Flood Attack Analysis

## 1. Understanding Network Attacks
Network attacks are malicious attempts targeting the network infrastructure to disrupt services, steal data, or gain unauthorized access. Common types include Denial-of-Service (DoS), Distributed Denial-of-Service (DDoS), IP spoofing, packet sniffing, and Man-in-the-Middle attacks.

## 2. Type of Attack Identified
Analysis of the Wireshark logs revealed a massive volume of TCP packets with the SYN flag set, originating from an unknown IP address. These packets did not receive the usual ACK response to complete the handshake, causing the server to keep many half-open connections.

This behavior clearly indicates a SYN Flood attack, a type of Denial-of-Service (DoS) attack where the attacker overwhelms the server with fake connection requests without completing the handshake.

## 3. Difference Between DoS and DDoS
- **DoS (Denial-of-Service):** Attack originates from a single device or source.
- **DDoS (Distributed Denial-of-Service):** Attack is launched from multiple devices or sources (often a botnet), increasing its scale and making it harder to detect or mitigate.

## 4. Why the Website was Slow and Showed Timeout Errors
The server became overwhelmed trying to manage thousands of incomplete connection requests, leaving it unable to respond to legitimate users, which led to significant delays and eventual service downtime.

## 5. Normal TCP 3-Way Handshake Process
- **SYN:** Client sends a connection request to the server.
- **SYN-ACK:** Server acknowledges and responds to the client.
- **ACK:** Client sends a final acknowledgment, completing the connection.

## 6. What Happens During a SYN Flood Attack
- The attacker sends a flood of SYN packets without completing the handshake with ACKs.
- The server holds these half-open connections, waiting for completion.
- Resources such as memory and CPU become exhausted due to the backlog.
- Legitimate connection attempts are denied or delayed.

## 7. Wireshark Log Findings
- Extremely high number of SYN packets from suspicious IP(s).
- Absence of ACK packets completing connections.
- Indicative of SYN Flood activity causing resource exhaustion.

## 8. Impact on the Network and Business
- Employees and customers were unable to access the website.
- Service disruptions impacted support, sales, and booking systems.
- Potential financial losses and damage to company reputation.

## 9. Immediate Actions Taken
- Temporarily shut down the server to relieve the load.
- Blocked the suspicious IP address via firewall rules.

## 10. Recommendations for Future Mitigation
- Enable TCP SYN Cookies to prevent resource exhaustion from half-open connections.
- Deploy Intrusion Detection Systems (IDS) to monitor suspicious traffic.
- Implement rate limiting on connection attempts per IP address.
- Use a Web Application Firewall (WAF) for application-level protection.
- Collaborate with Internet Service Providers (ISP) for traffic filtering and attack mitigation.
- Employ stateful firewalls to track and filter session states.

## 11. Important Security Note
SYN Flood attacks often utilize IP spoofing, making IP blocking a temporary fix. A layered security approach is necessary for effective prevention and mitigation.

## Conclusion
This report highlights how a SYN Flood attack can severely disrupt organizational services by exhausting server resources. It emphasizes the importance of proactive monitoring, immediate response, and comprehensive security measures to protect critical network infrastructure.
