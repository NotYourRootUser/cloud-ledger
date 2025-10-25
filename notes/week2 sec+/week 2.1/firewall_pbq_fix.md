# Firewall PBQ Fix — ACL Order + Subnet Scope

**Problem:**  
Users couldn’t access HTTPS due to mis-sequenced ACL; external users reached DMZ because the /8 subnet was too broad.

**Root Cause:**  
1. Deny SSH rule appeared before Allow HTTPS.  
2. Source range 10.0.0.0/8 was overly permissive.

**Fix Implemented:**  
- Reordered rules: Allow HTTPS first, Deny SSH second.  
- Narrowed subnet: replaced /8 with 10.1.0.0/24.  
- Verified DMZ remains isolated.

**Verification:**  
- Internal 10.1.0.25 → HTTPS  
- External 203.0.113.5 → SSH 
- Random UDP → Implicit Deny 

**Key Lesson:**  
> “Order defines logic. Scope defines exposure.”  
Top-to-bottom evaluation + tight CIDR = secure network.
