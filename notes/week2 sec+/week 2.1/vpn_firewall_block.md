# VPN & Firewall Logic – Short Notes (Security+ Week 2)

Firewalls read rules from **top to bottom**.  
Each packet that hits the firewall starts again at the **first rule**, not where the last one left off.  
As soon as a packet matches a rule, the firewall applies that action and stops checking.  
Anything that doesn’t match any rule is automatically denied at the end.

**Simple rule flow:**  
allow what you need → block everything else → finish with a deny all.

---

## IPsec / VPN Traffic Flow

A working IPsec VPN always uses **three types of traffic**:
- **UDP 500** – IKE (key exchange, Phase 1)  
- **UDP 4500** – NAT-Traversal (Phase 2, for clients behind NAT)  
- **Protocol 50 (ESP)** – carries the actual encrypted data  

Without ESP, the tunnel “connects” but no data moves.  
Some setups may also use **Protocol 51 (AH)** for integrity checks instead of encryption.

**Firewall checklist for IPsec:**
1. Allow UDP 500 → VPN gateway  
2. Allow UDP 4500 → VPN gateway  
3. Allow IP Protocol 50 → VPN gateway  
4. Deny everything else

---

## Firewall Ordering Logic

1. Put specific **allow** rules first (HTTPS 443, SSH 22, IPsec 500/4500/50).  
2. Then add **targeted deny** rules for each protected host.  
3. End with a single **Deny All** to catch anything missed.  

This order keeps traffic predictable and least-privilege compliant.

---

## Ports & Protocols People Mix Up

- **ESP 50** – not TCP/UDP, it’s its own IP protocol (used for IPsec data).  
- **AH 51** – IPsec integrity-only protocol, no encryption.  
- **L2TP 1701/UDP** – needs IPsec for security.  
- **GRE 47** – raw IP protocol used by PPTP and some site-to-site tunnels.  
- **PPTP 1723/TCP + GRE 47** – legacy VPN method.  
- **RADIUS 1812/1813 UDP** vs **TACACS+ 49 TCP** – both AAA, but different transports.  
- **SNMP 161/162 UDP** – 161 for queries, 162 for traps.  
- **Syslog 514 UDP** – log collection.  
- **NTP 123 UDP** – time sync.

---

### Quick Anchor
Firewalls don’t “remember” sessions — they check every packet.  
VPNs work only when **500, 4500, and 50** are allowed.  
Always finish your rule list with an explicit **deny all**.
