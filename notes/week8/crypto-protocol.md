# Security Plus Crypto and Protocol Notes

## MIME and S/MIME
**MIME**  
Rich email format. Supports images, video, audio, HTML, attachments.

**S/MIME**  
MIME with encryption, authentication, integrity, and digital signing.

**Digital Signing**  
Proves the sender is authentic and proves the message was not altered.

---

## SFTP and SSH
**SFTP**  
Secure file transfer over SSH. Uses port 22. If port 22 is blocked, SFTP is blocked.

**SSH**  
Encrypted remote shell plus optional tunneling.  
Remote shell allows executing commands on a remote machine.  
Tunneling allows other traffic to be carried inside SSH's encrypted channel.

**How SSH encrypts**  
Public key handshake to establish trust.  
Switches to fast symmetric encryption for the session.

---

## IPsec
**IPsec Purpose**  
Encryption, integrity, authentication for IP traffic.

**Why Layer 3**  
IP addresses and routing live at Layer 3, so IPsec protects packets at the network layer.

**Two Core IPsec Protocols**  
AH (Authentication Header)  
ESP (Encapsulating Security Payload)

**AH**  
Integrity and authentication only. Breaks with NAT because AH checks parts of the IP header that NAT modifies.

**ESP**  
Confidentiality, integrity, authentication. ESP provides encryption.

---

## VPN
**Definition**  
Encrypted tunnel across a public network.

**Why VPN is not Zero Trust**  
Traditional VPN trusts you once connected. Zero Trust requires continuous verification.

**What VPN hides**  
Hides your IP address. Encrypts all traffic between you and the VPN server.

---

## SRTP
**Definition**  
Secure Real Time Transport Protocol. Protects live audio and video streams.

**Why not TLS**  
TLS rides on TCP. TCP creates delay due to reliability and ordering.  
Real time traffic uses UDP for speed and low latency.

**Examples**  
Used in Teams, Zoom, WebRTC.

---

## Wi-Fi Crypto
**CCMP**  
AES based Wi-Fi encryption. Used in WPA2.

**TKIP**  
Temporary fix for weak WEP. Added dynamic keys and integrity checks.  
Banned today due to modern vulnerabilities.

**WEP**  
Original Wi-Fi encryption. Weak due to short keys and predictable key reuse.

---

## Deprecated Cryptography
DES  
MD5  
SHA-1  
RC4  
SSL

All are deprecated due to vulnerabilities.

---

## Hash Functions Overview
**MD5**  
128 bit hash. Broken due to collisions.

**SHA-1**  
160 bit hash. Collisions possible. Replaced by SHA-256 and SHA-3.

