# Firewall Notes (Security+)

- **What it is:** Packet-filtering device or service that enforces network traffic rules by IP, port, and protocol. Acts as a choke point between networks.

## Types
- Stateless (packet filter) → examines each packet individually.
- Stateful → tracks connection state (sessions).
- Next-Gen Firewall (NGFW) → application-level inspection, IDS/IPS integration.
- Web Application Firewall (WAF) → application-layer (Layer 7) protection for web apps.

## Detection / How issues show up
- Logs showing blocked/allowed rules and repeated denies.
- Unexpected drops of required ports/services.
- Alerts from SIEM when rule hits spike.
- Application errors if WAF blocks legitimate payloads.

## CIA Impact
- **Availability:** Medium (misconfig can block legit users).
- **Confidentiality / Integrity:** Medium (filters can prevent attacks that affect CIA).

## Practical mitigations / Best practice
- Apply default-deny (deny all, allow specific).
- Use layered rules (network ACLs + SGs + firewall).
- Keep rule sets minimal, documented, and reviewed regularly.
- Use NGFW for app-layer context + integrate with IDS/IPS.
- Test rule changes in a staging window; use logging and monitoring.

## One representative tool/service
- **pfSense / Cisco ASA / Palo Alto NGFW** for on-prem.  
- **WAF:** ModSecurity, AWS WAF for web apps.

## Quick analogy
- Firewall = bouncer at the club door: checks who’s allowed by the rules and keeps troublemakers out.
