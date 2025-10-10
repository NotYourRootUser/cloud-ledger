# Week 2.1 — Firewall, Network Flow & Defense-in-Depth Integration

## Overview
Week 2.1 focused on fixing my understanding of how traffic truly flows across network devices, from the Internet edge to internal subnets.  
I rebuilt my notes and PBQs around rule order, segmentation, and secure flow design, then capped the week with a **Defense-in-Depth × Zero-Trust** compression artifact to unify every control layer.

---

## Main Topics
| Focus | Outcome |
|-------|----------|
| **DMZ Rules** | Separated inbound vs outbound traffic with dual firewalls. |
| **ACL Order** | Reinforced “top-to-bottom → first match wins.” |
| **VPN (IKEv2)** | Understood Phase 1 (authentication) + Phase 2 (data tunnel). |
| **Security Groups vs NACLs** | SG = stateful, NACL = stateless → used for different tiers. |
| **VLAN & Subnetting** | Mapped logical network isolation inside a VPC. |
| **NAT vs IGW** | Why private networks need NAT to reach Internet safely. |
| **Load Balancers & Proxies** | Compared L4 vs L7 + Forward/Reverse flows. |
| **Defense-in-Depth / Zero-Trust** | Combined all devices into one layered secure architecture. |

---

## Files in This Folder
| File | Description |
|------|--------------|
| `dmz_rule_table.md` | Inbound/outbound firewall rules for DMZ placement. |
| `firewall_pbq_fix.md` | Fixed rule-order logic errors from previous PBQ. |
| `ikev2_notes.md` | Breakdown of IKEv2 Phase 1 & Phase 2. |
| `ids_ips_waf_onepager.md` | Summary of IDS vs IPS vs WAF. |
| `nat_igw_chart.md` | NAT vs Internet Gateway comparison. |
| `sg_vs_nacl_quick.md` | Fast recall table for SG vs NACL behavior. |
| `vlan_subnet_matrix.md` | VLAN vs Subnet mapping + diagram. |
| `lb_proxies.md` | L4/L7 load balancers + Forward/Reverse proxy notes. |
| `defense_in_depth.md` | Final compression artifact → Defense-in-Depth × Zero-Trust. |

---

## What I Learned
- Rule order matters as much as rule logic.  
- DMZs are real isolation buffers, not just theory.  
- VPN phases separate auth vs encryption responsibilities.  
- Load balancers + proxies control *how* and *where* traffic moves.  
- The entire system only makes sense once viewed as **layered verification gates** (Defense-in-Depth).  

---

## Anchor Quote
> “Only Web ↔ DB; Internet → DMZ → DB. Every connection should have a reason to exist.”

---

## Next Up
- Practice additional AWS VPC builds using Security Groups + NACL combinations.  
- Run a small lab tracing full flow: **Internet → WAF → ALB → App → DB.**  
- Begin **Week 3 – Identity & Access Management (AAA / SSO / Federation)**.

---
