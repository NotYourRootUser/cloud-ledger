# Network Telemetry Notes

## Anchor
Network telemetry is about collecting data that shows how information flows through a network. 
SPAN or TAP ports mirror packets for monitoring. NetFlow summarizes connection metadata—who talked to whom, when, and how much. 
AWS uses VPC Flow Logs as a cloud version of NetFlow. Packet captures like tcpdump show full payloads, similar to watching CCTV footage rather than reading reports. 
Telemetry helps detect anomalies, bandwidth spikes, and data exfiltration.

## Reverse
Collecting too much telemetry can flood storage or expose sensitive payloads. 
Full packet captures may include passwords or API keys if not filtered. 
Telemetry should be scoped by risk: metadata almost everywhere, payloads only where visibility is crucial.
