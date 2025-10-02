# Firewall, VPN, VLAN Notes

## Firewall Rules
- Deny All by default
- Allow HTTPS (443) → Web Server
- Allow Admin SSH (22) → Web Server
- Block SQL (1433) from Internet
- Watch for trap protocols (SMTP/IMAP)

## VLAN
- Virtual LAN = traffic isolation
- Finance VLAN must not communicate with Guest VLAN

## DMZ
- Protects internal LAN, only public-facing web allowed