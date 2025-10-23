# IDS vs IPS vs NIDS / HIDS Notes

## Anchor
IDS stands for Intrusion Detection System. It observes network or host activity and generates alerts when behavior looks suspicious. IPS stands for Intrusion Prevention System. It inspects traffic inline and can block or drop malicious traffic in real time. NIDS refers to network based systems that monitor traffic on network links. HIDS refers to host based systems that run on individual machines and monitor logs, file integrity, and process activity.

A common deployment pattern is to mirror traffic from a switch to a NIDS sensor for passive analysis while placing an IPS inline at critical network choke points. Security Onion, Suricata, and Zeek are common tools for network detection. Wazuh and OSSEC are common host based options. A practical example is using Zeek on a network span port to create logs for connection activity while running Suricata in IPS mode on the outbound gateway to block known bad signatures.

## Reverse
If an IPS is configured too aggressively it can generate false positives that block legitimate traffic and disrupt operations. Detection systems that are too permissive will miss attacks. Host based systems provide deep local context but need maintenance on each machine. Network sensors provide broad visibility but lack host context. Tuning is required to reduce noise and avoid alert fatigue. Ensure logging is centralized, alerts are triaged, and blocking rules are tested in a staging environment before enabling them in production.
