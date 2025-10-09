## Wireless Security Architecture — Notes

- **WPA3** replaces WPA2-PSK with **SAE (Simultaneous Authentication of Equals)** to prevent offline brute-force attacks.  
- **802.1X** enforces network access control; authentication runs through **EAP-TLS → RADIUS → AD/LDAP**.  
- The **firewall** is a three-legged design: **outside (Internet)**, **DMZ**, and **inside (LAN)** interfaces.  
- **Corporate SSID (WPA3-Enterprise)** uses mutual certificate authentication via EAP-TLS.  
- **Guest SSID (Captive Portal)** operates on an isolated VLAN with Internet-only routing.  
- **Access Points (APs)** connect to an **AP Controller** over a dedicated **Management VLAN**, separate from data paths.  
- **RADIUS server** communicates securely with **AD/LDAP** for user identity validation.  
- **IDS/IPS TAP** monitors wireless aggregation; logs and alerts flow to the **SIEM** for visibility.  
- **Segmentation + Monitoring** ensure reduced attack surface and improved detection.  

### Compression Anchor
> *"Wireless = Authenticate → Encrypt → Isolate → Monitor."*

### Memory Anchor
**RADIUS DIAGRAM** — R (RADIUS) · A (AP) · D (DMZ) · I (IDS) · U (User VLAN) · S (SIEM)

