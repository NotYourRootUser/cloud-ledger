# Man-in-the-Middle (MITM) Notes (Security+)

- **What it is:** Attacker sits between two communicating parties, intercepting or altering traffic without them knowing.

## Types
- Passive → just listens (sniffing).
- Active → modifies or injects traffic.

## Examples
- ARP spoofing → fake ARP replies redirect traffic.
- Evil Twin Wi-Fi → fake AP collects credentials.
- HTTPS downgrade → strips or weakens TLS.

## Mitigation 
- Use strong encryption (TLS/HTTPS, VPN).
- Enforce HSTS and certificate pinning (clients + servers).
- Secure Wi-Fi (WPA3, 802.1X Enterprise).
- Use network segmentation (VLANs) to limit broadcast domains.
- Enable Dynamic ARP Inspection (DAI) on managed switches.
- Configure switch port security (sticky MACs, max-MAC, shutdown).
- Implement Network Access Control (NAC) to approve endpoints.
- Implement IDS/IPS and behavior analytics for early detection
- Apply WAF for application-layer protection where relevant.
- Harden TLS (disable weak ciphers, enforce TLS1.2+/PFS).
- Use secure DNS (DNS over TLS/HTTPS) to avoid DNS manipulation.
- Centralized logging + alerting (SIEM/CloudWatch/ELK) for anomalies.

| Category                                | What to Remember                     | Example Controls                                                    |
| --------------------------------------- | ------------------------------------ | ------------------------------------------------------------------- |
| **1. Encryption Controls**              | Stop interception at the data layer. | TLS/HTTPS, VPN, HSTS, Certificate Pinning                           |
| **2. Wireless Security**                | Stop Wi-Fi MITM (Evil Twin).         | WPA3, 802.1X Enterprise, Disable open networks                      |
| **3. Network Infrastructure Hardening** | Stop LAN MITM (ARP spoofing).        | Dynamic ARP Inspection (DAI), Port Security, NAC, VLAN Segmentation |
| **4. Monitoring & Detection**           | Spot it early.                       | IDS/IPS, SIEM logging, Behavior analytics                           |


## Containment
- Disconnect affected host(s) from the network immediately.  
- Block attacker’s MAC/IP at switch, firewall, or WAF.  
- Flush/clear ARP cache entries on impacted systems.  
- Disable rogue DHCP servers or rogue access points.  
- Force re-establish secure sessions (new TLS handshake).  

## Detection
- Cert warnings in browsers.
- Duplicate MAC/IP entries in ARP tables.
- IDS/IPS alerts on ARP spoofing or odd TLS handshakes.
- Packet captures with asymmetric flows.

## CIA Impact
- **Confidentiality:** High
- **Integrity:** High
- **Availability:** Low

## Tool
- Wireshark (detect unusual ARP/TLS).
- Ettercap (known MITM tool).

## Analogy
- Like someone repeating or changing words in a conversation while pretending to be invisible.
