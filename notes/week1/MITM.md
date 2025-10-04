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
- Strong encryption (TLS/HTTPS, VPN).
- Wi-Fi protections (WPA3).
- Certificate pinning + HSTS.
- MFA for extra trust.

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
