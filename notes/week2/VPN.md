# VPN Notes (Security+)

- **What it is:** Virtual Private Network — creates an encrypted tunnel across an untrusted network so remote endpoints can communicate securely.

## Types / Protocols recap
- Remote Access vs Site-to-Site.
- Protocols: IPSec (ESP/AH), IKEv2, SSL/TLS VPNs, L2TP/IPSec.
- Tunnel types: Full vs Split.

## Detection / How issues show up
- User reports of failed connections or cert errors.
- VPN logs showing repeated auth failures or sudden session drops.
- IDS alerts for unexpected VPN traffic patterns or anomalous source IPs.
- Increased latency or resource issues at gateway (overloaded concentrator).

## CIA Impact
- **Confidentiality:** High (protects data in transit).
- **Integrity:** High (ensures data not tampered on the wire).
- **Availability:** Medium (gateway outage or overloaded VPN can prevent access).

## Practical mitigations / Best practice
- Enforce strong authentication (MFA + certificates).
- Prefer full-tunnel where sensitive traffic must be protected; consider split-tunnel risks.
- Use up-to-date protocols (IKEv2/IPSec or TLS-based) and strong ciphers.
- Limit access by policy (least privilege, network segmentation).
- Monitor VPN logs, session lengths, and concurrent sessions; patch concentrators/gateways.

## One representative tool/service
- **OpenVPN / Cisco AnyConnect / AWS Client VPN** (know names and purpose).

## Quick analogy
- VPN = private train tunnel through a rough area — traffic inside the train is hidden from outside observers.
