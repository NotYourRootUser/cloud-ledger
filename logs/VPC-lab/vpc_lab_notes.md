# AWS VPC Lab — Block 2 Notes
**Date:** 2025-10-07  
**Block:** 6:45 – 8:45 AM  
**VPC ID:** vpc-0ff99c91f32a361ea

---

##  VPC & Subnets
- CIDR: 10.0.0.0/16  
- Public Subnet: 10.0.1.0/24  
- Private Subnet: 10.0.2.0/24  
- AZ: ap-southeast-2a  
- DNS Hostnames: Enabled  

 **Concept Hook:**  
“/24 = network + 8 bits for hosts → 256 IPs.”

---

##  Internet Gateway (IGW)
- Name: lab-igw  
- Attached to VPC   
- Enables outbound Internet from **public** subnet.

 **Recall:** IGW = bridge between VPC and Internet.

---

##  Route Tables (To Do next block)
| Table | Default Route | Target | Associated Subnet |
|--------|----------------|---------|-------------------|
| rtb-public | 0.0.0.0/0 | IGW | lab-public |
| rtb-private | 0.0.0.0/0 | NAT | lab-private |

---

## NAT Gateway (To Do next block)
- Subnet: lab-public  
- Elastic IP: [will record here]  
- Allows private subnet outbound traffic.

---

## Connectivity Test (To Do next block)
- Ping from private EC2 → Internet (via NAT)  
- Ping from public EC2 → Internet (via IGW)

---

## Reflection
**What clicked:** CIDR structure and why IGW ≠ NAT.  
**What’s next:** Build route tables + NAT tomorrow (Block 2 continuation).  
**Compression Line:** “Public = IGW path; Private = NAT path.”
