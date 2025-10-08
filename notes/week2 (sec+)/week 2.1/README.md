# Week 2.1 — Firewall & Network Flow Fixups

## Overview
This week I focused on fixing my understanding of how firewalls, VPNs, and network flow actually work together.  
I went back through my Security+ notes and AWS networking labs to make sure I really understood what traffic should be allowed, blocked, or routed through. Hence week 2.1, week 2 revamped to fully understand.

---

## Main Topics
- **DMZ Rules** → How inbound and outbound traffic gets separated with two firewalls.  
- **ACL Order** → Rules are checked from top to bottom, and the first match decides what happens.  
- **VPN (IKEv2)** → Learned how secure tunnels are built in two phases (authentication + data).  
- **Security Groups vs NACLs** → SGs are stateful, NACLs are stateless — both used for different layers.  
- **VLAN & Subnetting** → How logical networks (VLANs) connect to subnets in a VPC.  
- **NAT vs IGW** → Why private networks need NAT to reach the internet safely.

---

## Files in This Folder
| File | Description |
|:--|:--|
| `dmz_rule_table.md` | Notes on inbound/outbound firewall rules in a DMZ. |
| `firewall_pbq_fix.md` | Fixed a firewall PBQ where rules were in the wrong order. |
| `ids_ips_waf_onepager.md` | Quick summary of IDS, IPS, and WAF differences. |
| `ikev2_notes.md` | What happens during Phase 1 and Phase 2 of IKEv2. |
| `nat_igw_chart.md` | Side-by-side comparison of NAT vs Internet Gateway. |
| `sg_vs_nacl_quick.md` | Easy table for remembering SG vs NACL behavior. |
| `vlan_subnet_matrix.md` | VLAN vs subnet comparison + diagram notes. |

---

## What I Learned
- Firewalls don’t just “block or allow” — the order of rules actually matters a lot.  
- A DMZ isn’t just a buzzword; it’s a real buffer zone between public and private networks.  
- VPNs use ports like 500, 4500, and 1701 — each step in IKEv2 has a purpose.  
- Drawing network flow diagrams helped me see the logic visually instead of just memorizing.

---

## Anchor Quote
> “Only Web ↔ DB; Internet ↛ DB.”  
> Everything in the flow should have a reason to connect.

---

## Next Up
- Practice more AWS VPC builds with proper subnets and gateways.  
- Try a small lab tracing traffic from Internet → Web → DB.  
- Review Security+ PBQs on firewall and ACL logic under time pressure.

