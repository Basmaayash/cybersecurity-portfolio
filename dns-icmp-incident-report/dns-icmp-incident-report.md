🛡️ Cybersecurity Incident Report: Network Traffic Analysis
🧩 Part 1: Problem Summary (DNS and ICMP)
Network traffic analysis showed failed attempts by a user’s browser to access a website. The browser sent a DNS query using UDP port 53 to resolve the domain name, but no valid response was received from the DNS server. Instead, an ICMP error was returned:

“Destination unreachable (port unreachable)”

📄 tcpdump Log Summary:
Time: 13:24:32.192571
Client IP: 192.51.100.15
DNS Server IP: 203.0.113.2
Protocol: UDP
Destination Port: 53
Response: ICMP – "Destination port unreachable"
Repetition: 3 identical ICMP error messages
❓ Possible Cause:
The DNS server may have been misconfigured, offline, or a firewall blocked inbound/outbound UDP port 53 traffic.

🔍 Part 2: Analysis and Root Cause
🕒 Time of incident: 1:24 PM
📢 Reported by: Multiple users who couldn’t access www.yummyrecipesforme.com
⚠️ Error shown: “Destination port unreachable”
🧪 Investigation Steps:
Captured packets using tcpdump
Observed repeated DNS queries sent via UDP to port 53
Received ICMP “port unreachable” responses
Verified DNS availability from another host
Audited firewall rules
Used tools (nslookup, dig, systemctl) to validate DNS service status
🧾 Findings:
DNS resolution failed
No response from DNS server
ICMP error confirms port 53 is not reachable
No return traffic from DNS server observed
🔍 Root Cause (likely):
The DNS service was either down, not listening on port 53, or a firewall was blocking UDP traffic on that port.

✅ Recommended Actions:
Check DNS service status using: systemctl status named
Update firewall to allow UDP traffic on port 53
Implement DNS uptime monitoring
Set up alerting for ICMP error spikes
Add secondary DNS server for redundancy
This report was created as part of the Google Cybersecurity Certificate program. It reflects real-world diagnostic and incident response techniques using tools like tcpdump and standard network analysis protocols.
