# Security+ PBQ Set 2 – Recap and Corrections

This set covers the main network placement and logic questions that always show up on Security+.  
It includes what I did first, what was wrong, and what the correct reasoning looks like.

---

## PBQ 1 – DMZ and Server Placement

**Scenario:** Decide where to place web, mail, DNS, and database servers.

**My first layout:**  
`Internet → DNS → Edge Firewall → Web/Mail → Internal Firewall → LAN + DB`

**What was wrong:**  
I put DNS in front of the firewall. That exposes it directly to the internet — bad idea.

**Correct layout:**  
`Internet → Edge Firewall → [DMZ: Web / Mail / Public DNS] → Internal Firewall → [LAN: Internal DNS / Database]`

**Takeaway:**  
- Public-facing servers belong in the DMZ.  
- Anything internal (like the DB or internal resolver) stays behind the internal firewall.  
- *Public DNS = DMZ, Internal DNS = LAN.*

---

## PBQ 2 – VPN Concentrator + IDS/IPS Placement

**Scenario:** Combine remote-access VPN, DMZ, IDS, and IPS correctly.

**My first layout:**  
`Internet → Edge FW → DMZ VPN → IDS → Internal FW → IPS → LAN`

**What was off:**  
The IDS was too deep in the network, and the VPN looked like it sat inside the DMZ.

**Correct layout:**  
`Internet → Edge FW → IDS → (DMZ │ VPN) → Internal FW → IPS → LAN`

**Notes:**  
- The IDS should sit right after the edge firewall so it can watch filtered inbound traffic.  
- The VPN concentrator is on a separate path beside the DMZ, not inside it.  
- The IPS stays inline right before the LAN.

**Quick rule:**  
Firewall filters → IDS watches → DMZ/VPN in parallel → Internal FW → IPS blocks → LAN.

---

## PBQ 3 – VLAN Segmentation and Trunking

**Scenario:** Three departments and a shared printer. Need isolation and VLAN-hopping protection.

**Final setup:**  
- VLAN 10 → HR (Access Port 1)  
- VLAN 20 → Finance (Access Port 2)  
- VLAN 30 → IoT (Access Port 3)  
- VLAN 99 → Printer (Access Port 4)  
- Switch ↔ Router link is a **trunk** with **802.1Q tagging**.  
- The router uses sub-interfaces (.10, .20, .30, .99) to route between VLANs.

**Defenses:**  
- Disable DTP or force ports to access mode.  
- Disable or move unused ports into an unused VLAN.  
- Change the native VLAN from VLAN 1.

**Remember:**  
Access = untagged.  
Trunk = tagged.  
Routing happens on the router (“router-on-a-stick”).

---

## PBQ 4 – ACL Rule Logic and Overlap

**Scenario:** Host 192.168.1.25 tries to SSH (port 22) through this rule set:

| # | Source | Port | Action |
|---|---------|------|--------|
| 1 | 192.168.1.0/24 | 22 | Allow |
| 2 | 192.168.1.25 | Any | Deny |
| 3 | Any | Any | Deny |

**What actually happens:**  
192.168.1.25 is part of 192.168.1.0/24, so Rule 1 matches first and allows SSH.  
The specific deny never triggers.

**Fixed order:**  
1. Deny 192.168.1.25 → Any → Any  
2. Allow 192.168.1.0/24 → Any → 22  
3. Deny Any → Any → Any

**Lesson:**  
ACLs read top-to-bottom.  
The first match wins.  
Always put specific rules before broader ones.

---

## Quick Summary Table

| PBQ | Core Concept | Wrong Idea | Correct Idea | Shortcut to Remember |
|------|---------------|-------------|---------------|-----------------------|
| 1 | DMZ buffer zone | DNS before FW | Public DNS in DMZ, internal DNS in LAN | “Public out, private in.” |
| 2 | Layered perimeter | VPN inline | VPN beside DMZ, IDS before DMZ, IPS before LAN | “FW → IDS → DMZ/VPN → FW → IPS → LAN.” |
| 3 | VLAN segmentation | No trunk logic | Access → Trunk (tagged) → Router | “Access untagged, trunk tagged.” |
| 4 | ACL evaluation | Specific after broad | Specific first | “First match wins.” |

---

