# IoT Segmentation & Firmware Hardening

## Why IoT Is Risky
IoT gear ships with weak creds, outdated firmware, and minimal logging.  
Once compromised, it’s a pivot point into internal systems.

---

## Segmentation Notes
Keep IoT on its own VLAN or subnet.  
Treat that space like a quarantine zone talk only to what’s required.  
Use ACLs and firewall rules to stop traffic back into the corporate LAN.  
Example: cameras → IoT VLAN → firewall → management zone → storage server.

[Edge IoT VLAN] → [Firewall/UTM] → [Mgmt Zone] → [Core Network]
- Each hop should be monitored and locked down to least privilege.

---

## Firmware Hardening
- Sign and verify firmware before install.  
- Enforce version control; block rollback.  
- Secure boot so unsigned images never load.  
- Test updates in a sandbox before deployment.

---

## Defender Rule
Keep IoT isolated, firmware verified, and update paths logged.  
If it talks where it shouldn’t, block first, ask later.

---

## Quick Points
| Area | Focus |
|------|--------|
| Risk | Weak firmware, easy pivot |
| Segmentation | VLANs, ACLs, firewall |
| Hardening | Signed code, version check |
| Defender Move | Contain edge, protect core |
