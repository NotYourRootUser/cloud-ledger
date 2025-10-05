# VLAN Notes (Security+)

- **VLANs** operate at **Layer 2 (Data Link)** but influence Layer 3 routing when used with inter-VLAN routing or Layer 3 switches.

- **What it is:** Virtual LAN — logical segmentation of a switch/network into separate broadcast domains without requiring separate physical hardware.

## Use cases
- Separate user groups (HR, Finance, Guests).
- Isolate servers, IoT devices, and management networks.
- Limit broadcast domains and reduce attack surface.

## Common Attacks
- VLAN hopping (double tagging, switch spoofing)
- Misconfigured trunk ports exposing sensitive VLANs

## Detection / How issues show up
- Unexpected traffic crossing VLANs (misconfig or trunking issues).
- Devices in wrong VLAN after DHCP lease renewal.
- Inter-VLAN routing misconfig or firewall rules allowing unwanted access.
- VLAN hopping attempts (double-tagging) detected by suspicious tagged frames.

## CIA Impact
- **Confidentiality:** High (segmentation prevents lateral movement).
- **Integrity:** Medium (keeps attacker containment constrained).
- **Availability:** Medium (misconfiguration can cut off services).
x       
## Practical mitigations / Best practice
- Use access control lists and firewalling between VLANs (strong east-west controls).
- Disable unused switch ports; use port security and mac limiting.
- Use VLAN pruning only where needed; avoid unnecessary trunking.
- Protect against VLAN hopping: use native VLAN config best practices and switch hardening.
- Document VLAN IDs, purposes, and mapping to physical ports.

## One representative tool/feature
- Managed switches (Cisco Catalyst, Aruba) with port security and 802.1Q tagging.

## Quick analogy
- VLAN = apartment building with locked doors between apartments; each tenant lives in their own space unless permitted to visit.
