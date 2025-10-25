# Week 2.1 — Firewall & Network Flow Fixups

## Overview
This week I focused on tightening my understanding of how network traffic actually moves through each layer.  
Instead of memorizing firewall rules, I wanted to see *why* something is allowed, blocked, or routed.  
I rebuilt my Security+ notes, revisited AWS VPC traffic paths, and made sure every connection made logical sense.  
The week finished with a **Defense-in-Depth × Zero-Trust** summary that stitched all the pieces together.

---

## Main Topics
- **DMZ Rules** → How inbound and outbound traffic are split with dual firewalls.  
- **ACL Order** → Top-to-bottom rule processing; first match always wins.  
- **VPN (IKEv2)** → Phase 1 = auth, Phase 2 = data tunnel.  
- **Security Groups vs NACLs** → SG = stateful, NACL = stateless.  
- **VLAN + Subnetting** → How logical networks connect inside a VPC.  
- **NAT vs IGW** → Why private subnets need NAT to reach the internet safely.  
- **Load Balancers & Proxies** → Difference between L4 vs L7 balancing, forward vs reverse proxy.  
- **Defense-in-Depth / Zero-Trust** → Final compression diagram tying every control layer together.

---

## Files in This Folder
| File | Description |
|------|--------------|
| `dmz_rule_table.md` | Inbound/outbound firewall rule logic for DMZ placement. |
| `firewall_pbq_fix.md` | Fixed PBQ error on rule order. |
| `ikev2_notes.md` | Step-by-step of IKEv2 Phase 1 & 2. |
| `ids_ips_waf_onepager.md` | One-pager comparing IDS / IPS / WAF. |
| `nat_igw_chart.md` | NAT vs IGW side-by-side reference. |
| `sg_vs_nacl_quick.md` | Quick recall for SG vs NACL. |
| `vlan_subnet_matrix.md` | VLAN vs Subnet mapping + diagram. |
| `lb_proxies.md` | Notes on L4/L7 load balancers and forward/reverse proxies. |
| `defense_in_depth.md` | Compression artifact — full Defense-in-Depth × Zero-Trust model. |

---

## What I Learned
- Firewalls don’t just *block or allow* — **order matters** more than most people realize.  
- A DMZ isn’t theory; it’s the real buffer zone that protects private networks.  
- VPNs split their job cleanly: Phase 1 authenticates, Phase 2 encrypts.  
- Once I drew the flows, the logic behind ACLs, LBs, and proxies finally clicked.  
- Layered security isn’t overkill — it’s what keeps one mistake from collapsing the whole system.

---

## Anchor Quote
> “Only Web ↔ DB; Internet → DMZ → DB.”  
> Every connection should exist for a reason — no open paths without purpose.

---

## Next Up
- Keep practicing VPC builds that combine SG + NACL + route table logic.  
- Simulate a full flow: **Internet → WAF → ALB → App → DB**, trace packets end to end.  
- Start **Week 3 — Identity & Access Management (AAA / SSO / Federation)** to move from *verifying traffic* to *verifying identities*.

---
