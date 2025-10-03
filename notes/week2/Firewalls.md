# Firewall — Security+ Exam Recall Core

## Purpose
- Acts as the **first line of defense** between networks.  
- Controls traffic based on **IP address, port, and protocol**.  

## Types
- **Stateless Firewall**    
  - Examines each packet individually.  
  - Doesn’t remember prior traffic.  
- **Stateful Firewall**  
  - Tracks full sessions.  
  - Knows if packets belong to an existing, legitimate connection.  

## Rules
- **ACLs (Access Control Lists):** Define allow/deny actions by IP, port, and protocol.  
- Example:  
  - Deny TCP 23 (Telnet)  
  - Allow TCP 22 (SSH)  

## Placement
- Typically deployed at the **network perimeter** or between internal segments.  
- a **Web Application Firewall** (WAF) operates at **Layer 7** and can filter on **application-layer content (e.g., SQLi, XSS).**

## Limitations
- Cannot inspect encrypted traffic contents.  
- Cannot block application-layer attacks (SQLi, XSS, CSRF → handled by WAF).  

## Blue Team Filter
- **Contain** → Firewalls block/contain unauthorized traffic before it spreads into the internal LAN.  

---

## Exam Recall Anchors
- **Stateful vs Stateless?** → Stateful = tracks sessions; Stateless = packet only.  
- **Which port/service to block?** → Know common ports (Telnet 23, SSH 22, HTTP 80, HTTPS 443).  
- **What defense function is it?** → Contain.  
- **Plain-language analogy** → A firewall is the **gatekeeper at the door**, checking IDs (IP/port) before letting anyone in.  

### Diagram
![Firewall/VPN/IDS Diagram](./diagrams/firewall_vpn_ids.png)
