# 🧭 Security+ Week 3 — Completion Sheet
**Theme:** Encryption · Authentication · Access Control  
**Goal Date:** Friday (End of Week 3)

---

## 🎯 Friday Goal
✅ Fully recall, explain, and apply every concept below without notes  
✅ 1 practice exam ≥ 80 %  
✅ All artifacts uploaded (diagram + auth table + practice report)

---

## 1. Encryption & PKI
| Topic | What You Must Recall | Example Control / Tool |
|-------|----------------------|------------------------|
| **Symmetric vs Asymmetric** | Key count (1 vs 2), speed, use cases | AES / RSA |
| **Hashing** | Integrity only (no confidentiality) | SHA-256, HMAC |
| **Digital Signatures** | Hash + Private Key = authenticity + integrity | Code-signing cert |
| **Certificates & PKI Chain** | Root → Intermediate → Leaf; CRL vs OCSP | TLS cert hierarchy |
| **TLS/SSL** | Encrypts data in transit + authenticates server | HTTPS, VPN tunnels |
| **Perfect Forward Secrecy** | New session keys each handshake | Diffie-Hellman |

**Artifact:** 1-page diagram of TLS handshake + PKI chain.

---

## 2. Authentication Mechanisms
| Topic | Key Facts | Example Protocols |
|-------|-----------|------------------|
| **MFA Factors** | Something you *know / have / are* | Password + Token |
| **Federation & SSO** | Trust between domains → one login | SAML 2.0, OIDC |
| **RADIUS vs TACACS+** | UDP vs TCP / auth & accounting split | 802.1X Wi-Fi |
| **Kerberos** | TGT + ticket; mutual auth | AD logon |
| **LDAP** | Directory lookups → user attributes | Port 389/636 (SSL) |

**Artifact:** Comparison table (RADIUS · TACACS+ · Kerberos · LDAP · SAML).

---

## 3. Access Control
| Model | Rule | Example |
|--------|------|---------|
| **DAC** | Owner decides permissions | Windows share |
| **MAC** | Labels / clearances → system enforces | DoD networks |
| **RBAC** | Roles map to privileges | AWS IAM Groups |
| **ABAC** | Attribute-based (context, tags) | IAM policy conditions |

**Artifact:** 1 diagram mapping roles → resources → permissions.

---

## 4. VPN & Remote Access
| Type | Tunneling Protocol | Ports |
|------|--------------------|-------|
| **IPsec Tunnel** | ESP + AH + IKEv2 | 500/4500 |
| **SSL VPN** | HTTPS-based | 443 |
| **Split vs Full Tunnel** | Internet route split | Config policy |
| **Always-On VPN** | Auto-reconnect | Endpoint policy |

**Artifact:** mini-lab diagram VPN client ↔ gateway ↔ LAN.

---

## 5. Exam Drill & Compression
| Task | Target |
|------|---------|
| **45-Question Timed Set** | ≥ 80 % accuracy · explain why for missed Qs |
| **Written Compression Summary** | 5 lines (Encryption → Auth → Access) + 3 lens cross-links (e.g., Systems Thinking, Game Theory, Communication) |

**Artifact:** practice-exam report + 5-line summary .md

---

## ✅ Friday Checklist
- [ ] Explain AES vs RSA without notes
- [ ] Draw TLS handshake diagram
- [ ] List 3 PKI revocation methods
- [ ] Compare RADIUS vs TACACS+
- [ ] Describe Kerberos ticket flow
- [ ] Define RBAC vs ABAC with example
- [ ] Describe split vs full VPN tunnel
- [ ] Score ≥ 80 % on practice exam
- [ ] Upload all artifacts (diagram, tables, exam report)

---
