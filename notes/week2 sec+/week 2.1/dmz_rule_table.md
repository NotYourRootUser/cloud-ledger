## Foundation
DMZ = “demilitarized zone.”  
Acts as a **buffer** between the Internet and internal LAN.  
Hosts public-facing systems like **web or mail servers**.  
Uses **two firewalls**:  
- FW1 → between Internet & DMZ (handles inbound)  
- FW2 → between DMZ & LAN (handles outbound / lateral)

Goal: stop anything external from ever reaching the LAN directly.

---

## Anchor (Analogy)
Think of it like a **castle setup**:  
DMZ = moat.  
FW1 = outer drawbridge (checks who enters).  
FW2 = inner gate (protects the keep).  
Core ideas → **Isolation**, **Inspection**, **Least Privilege**.

---

## Scenario
Example: small org running a web app.  
Web server lives in the **DMZ**, DB lives on the **internal LAN**.  
Traffic rules:  
- Internet → DMZ → allow 80/443 (HTTP/HTTPS)  
- DMZ → DB → allow 3306 (MySQL only)  
No Internet → DB traffic ever allowed.  
Keep rules **tight**, remove **any-any**.

---

## Applied Rule Table

| # | Direction | Source Zone | Destination Zone | Port | Action | Purpose |
|---|------------|--------------|------------------|------|----------|----------|
| 1 | Internet → DMZ | TCP 80/443 | Allow | Public web access |
| 2 | DMZ → Internet | TCP 80/443 | Allow | Updates / responses |
| 3 | DMZ → Internal DB | TCP 3306 | Allow | Web → DB comms |
| 4 | Internal DB → DMZ | Any | Deny | Block reverse traffic |

---

## Misconfigs to Avoid
1. Exposed DB to Internet.  
2. Any-any rule on FW2.  
3. Hairpin routes that skip inspection.  

---

### Quick Summary
> DMZ = buffer zone.  
> Dual firewalls = two gates, both directions filtered.  
> Rule of thumb: isolation + least privilege always.  
