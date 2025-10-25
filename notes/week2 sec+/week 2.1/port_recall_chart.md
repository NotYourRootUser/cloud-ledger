**Network** is secure building. Each port = a door with a label. TCP doors are locked until a connection handshake, UDP doors are flap doors — open briefly for quick exchanges.

- Port 22 → Secure staff door (SSH admin access).
- Port 53 → Reception window (quick name lookups).
- Port 80/443 → Customer entrance (public web).
- Port 25 → Mail chute (outbound delivery).

[Client]
    ↳ :20 FTP-Data (TCP)
    ↳ :21 FTP-Control (TCP)
    ↳ :22 SSH (TCP)
    ↳ :25 SMTP (TCP)
    ↳ :53 DNS (UDP/TCP)
    ↳ :80 HTTP (TCP)
    ↳ :110 POP3 (TCP)
    ↳ :143 IMAP (TCP)
    ↳ :443 HTTPS (TCP)
    ↳ :3389 RDP (TCP)
[Server]

Compression Snapshot:

- **TCP** = reliable, connection-oriented.
- **UDP** = quick, stateless.
- Match port → service → purpose → defense control.