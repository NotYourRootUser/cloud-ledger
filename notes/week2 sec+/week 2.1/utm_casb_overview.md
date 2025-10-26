# UTM & CASB / Short Notes

**UTM (Unified Threat Management):**
- All-in-one perimeter device (firewall, IDS/IPS, AV, VPN, content filter).  
- Protects **north-south traffic** at the **edge of the network**.  
- Simplifies management but can add latency or become a bottleneck.  
- Think: *“Swiss-Army knife at the gateway.”*

**CASB (Cloud Access Security Broker):**
- Sits between users and cloud apps (e.g., M365, G Drive, AWS).  
- Protects **data in cloud services** — visibility, DLP, access control, threat detection.  
- Deploys via **proxy** or **API integration**.  
- Think: *“Security guard watching cloud usage.”*

**UTM vs CASB:**
- UTM = On-prem perimeter protection.  
- CASB = Cloud data & user policy enforcement.  
- Together: **UTM guards the perimeter; CASB guards the cloud.**

**Quick Placement:**
User → VPN → Firewall/UTM → Internet → SaaS (CASB monitors)

**Key Trade-Offs:**
- UTM: breadth > depth.  
- CASB: depth in cloud, less on-prem control.  
