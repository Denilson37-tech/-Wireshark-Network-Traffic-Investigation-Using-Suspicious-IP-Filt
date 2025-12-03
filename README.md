A short, real-life network investigation using Wireshark to check whether unusual outbound traffic was malicious or normal Windows activity.
1. Check Network Activity (CMD)

Before capturing traffic, I used CMD to confirm the system had an active internet connection.

📸 CMD Screenshot

2. Start Wireshark Capture

Opened Wireshark and began a live capture on the active network interface.

📸 Capture Screenshot

3. Filter the Suspicious IP

To isolate the unusual connection, I applied an IP filter:
ip.addr == <suspicious_IP>

4. Inspect Packet Details

I reviewed the protocols, DNS requests, and HTTP traffic to check for abnormal behavior.

Findings:

DNS queries → normal (Google DNS)

HTTP request → Windows NCSI /connecttest.txt

No repeated beaconing

No unknown domains or ports
If Suspicious, This Could Indicate

RAT beaconing

Botnet traffic

DNS tunneling

Data exfiltration
Final Conclusion

The traffic was legitimate Windows system activity, not malware.
This project demonstrates basic SOC skills: filtering, packet inspection, and identifying normal vs suspicious traffic.
