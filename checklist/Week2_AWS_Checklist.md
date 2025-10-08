# 🟦 AWS Week 2 — Completion Sheet
**Theme:** VPC · Subnets · Routing · Security Groups · NAT Gateway  
**Goal Date:** Friday

---

## 🎯 Friday Goal
✅ Fully deploy and verify a two-tier AWS VPC (public web + private DB)  
✅ Demonstrate secure connectivity and isolation  
✅ Upload diagram + screenshots + summary .md to GitHub

---

## 1. VPC & Subnets
| Topic | What to Know Cold | Proof Artifact |
|:------|:------------------|:---------------|
| **VPC Basics** | CIDR range, region, AZ mapping | VPC screenshot |
| **Public vs Private Subnet** | Who can reach Internet / who can’t | Subnet table |
| **Route Tables** | Default route → IGW vs NAT | Route table screenshot |

---

## 2. Internet & NAT Gateways
| Topic | Recall | Proof Artifact |
|:------|:--------|:----------------|
| **Internet Gateway (IGW)** | Allows inbound/outbound for public | IGW attachment proof |
| **NAT Gateway** | Outbound-only access for private | NAT config & ping test |
| **Connectivity Test** | Web → Internet ✅ · Private → Internet ✅ · Internet → Private ❌ | CLI ping output / curl results |

---

## 3. Security Groups & Access
| Topic | Recall | Proof Artifact |
|:------|:--------|:----------------|
| **Web-SG** | HTTP/HTTPS from 0.0.0.0/0 → EC2 | SG rule screenshot |
| **DB-SG** | Allow MySQL 3306 from Web-SG only | SG rule screenshot |
| **Default Behavior** | Deny-all inbound, allow-all outbound | Summary .md notes |

---

## 4. Validation & Monitoring
| Topic | Recall | Proof Artifact |
|:------|:--------|:----------------|
| **CloudWatch** | EC2 metrics + alarm setup | CloudWatch alarm screenshot |
| **CloudTrail** | View VPC + IAM events | CloudTrail log screenshot |
| **Diagram** | Full architecture (flow arrows + SGs) | Exported PNG diagram |

---

## ✅ Friday Checklist
- [ ] VPC + 2 subnets created with CIDR documented  
- [ ] IGW attached and public route verified  
- [ ] NAT Gateway deployed and private subnet tested  
- [ ] Web-SG and DB-SG rules applied correctly  
- [ ] Web page loads → DB unreachable directly  
- [ ] CloudWatch alarm configured (CPU > 70 %)  
- [ ] CloudTrail logs confirm EC2→S3 action  
- [ ] Architecture diagram + screenshots + summary pushed to GitHub

---
