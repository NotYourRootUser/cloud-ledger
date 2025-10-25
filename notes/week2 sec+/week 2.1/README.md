# Week 2.1 / Firewall and Network Flow Review

## Overview
This update tightened the technical flow from Week 2 and cleaned up how each firewall, proxy, and routing layer connects.  
Instead of memorizing rules, I worked on seeing how every packet moves, what’s allowed, blocked, or redirected and why.  
Each note and table in this folder was revised for clarity and structure so the entire network picture makes sense at a glance.

---

## Main Topics
- DMZ Rule Logic - mapping inbound and outbound paths across dual firewalls.  
- ACL Order - understanding first-match behavior in real cases.  
- VPN (IKEv2) - clarifying how Phase 1 handles authentication and Phase 2 encrypts data.  
- Security Groups vs NACLs - comparing stateful and stateless behavior.  
- VLAN + Subnetting - linking logical networks inside a VPC.  
- NAT vs IGW - why private subnets rely on NAT for safe outbound access.  
- Load Balancers & Proxies - visualizing L4 vs L7 differences and reverse proxy flow.  
- Defense-in-Depth & Zero-Trust - refining the final compression diagram.

---

## Files in This Folder
| File | Description |
|------|--------------|
| `dmz_rule_table.md` | Updated inbound/outbound firewall rule logic. |
| `firewall_pbq_fix.md` | Corrected PBQ example on rule order. |
| `ikev2_notes.md` | Step-by-step of IKEv2 tunnel setup. |
| `ids_ips_waf_onepager.md` | Comparison of IDS, IPS, and WAF functions. |
| `nat_igw_chart.md` | NAT vs IGW quick reference. |
| `sg_vs_nacl_quick.md` | Fast recall sheet for SG vs NACL behavior. |
| `vlan_subnet_matrix.md` | VLAN/Subnet mapping with visual flow. |
| `lb_proxies.md` | Short notes on load balancer and proxy roles. |
| `defense_in_depth.md` | Updated compression artifact combining all layers. |
| `utm_casb_overview.md` | Added summary of UTM and CASB integrations. |
| `wireless_architecture.md` | Extended notes on wireless segmentation. |

---

## What Changed
- Reworked folder layout for faster lookup and file consistency.  
- Cleaned heading formats and punctuation across all markdown files.  
- Added wireless and UTM/CASB coverage to complete Domain 4.2 scope.  
- Standardized anchor quotes and diagrams for future reuse.

---

## Anchor Quote
> “Every rule exists for a reason - if you can’t explain it, it doesn’t belong in the firewall.”

---

## Next Up
- Continue to **Week 3 — Secure Network Management and Remote Access.**  
- Apply the same clarity to configuration integrity, log pipelines, and RBAC automation.

