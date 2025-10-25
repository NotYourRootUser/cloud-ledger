## 1) Quick Definitions (DoD vs ZT)
- **Defense-in-Depth (DoD):** Multiple independent controls so no single failure exposes the system.
- **Zero-Trust (ZT):** Never trust by default; authenticate, authorize, and encrypt every request; least privilege; continuous verification.

## 2) Integrated Stack 
- Edge & Perimeter
- Transport & Distribution
- Application Mediation
- Detection & Telemetry
- Identity & Access
- Data Protection

## 3) Core Mapping Table 
| Layer           | Control Device          | Purpose                                               | Zero-Trust Principle              | Example (Cloud)           |
| --------------- | ----------------------- | ----------------------------------------------------- | --------------------------------- | ------------------------- |
| **Edge**        | Firewall / WAF          | Filters external traffic and blocks malicious sources | Verify before connect             | AWS WAF · Security Groups |
| **Transport**   | Load Balancer (L4 / L7) | Distributes traffic, can terminate TLS                | Policy enforcement at L7          | ALB / NLB                 |
| **Application** | Reverse Proxy / CASB    | Sanitizes and controls web/app access                 | Least-privilege access            | CloudFront / Zscaler      |
| **Detection**   | IDS / IPS / SIEM        | Detects intrusions · feeds alerts                     | Continuous validation             | GuardDuty · Security Hub  |
| **Identity**    | IAM / MFA / SSO         | Authenticates & authorizes every request              | Never trust · always verify       | AWS IAM Identity Center   |
| **Data**        | Encryption / DLP        | Protects data at rest and in transit                  | Encrypt everywhere · least access | KMS · Macie               |


## 4) Adversarial Rep — Attack paths & Mitigations

- **Exploit: Reverse proxy cache poisoning**
  - *What:* Attacker forces malicious or stale responses into reverse proxy cache, serving them to other users.
  - *Mitigation:* Restrict caching for authenticated content, validate cache keys (include host, scheme), sanitize headers and query strings before caching, set conservative cache TTLs.

- **Exploit: Header spoofing / Host header injection**
  - *What:* Forged Host or X-Forwarded-For headers cause incorrect routing/authorization or log poisoning.
  - *Mitigation:* Normalize and validate headers at the edge (WAF/ALB), require TLS with proper host validation, add strict host-based allowlists and logging correlation.

- **Exploit: TLS stripping via misconfigured proxy**
  - *What:* Man-in-the-middle downgrades HTTPS to HTTP if TLS termination/redirection is weak.
  - *Mitigation:* Enforce HSTS, redirect all HTTP to HTTPS at edge, perform TLS termination at trusted reverse proxy with strong ciphers, monitor for mixed-content warnings.

- **Exploit: Lateral movement through flat network (no micro-segmentation)**
  - *What:* Compromised host moves east-west to reach sensitive systems (RDP/SMB).
  - *Mitigation:* Implement micro-segmentation (VLANs, security groups), least-privilege ACLs, restrict management ports, require jump hosts and MFA for remote access, monitor with IDS/IPS.

- **Exploit: Misconfigured load balancer / sticky session misuse**
  - *What:* Improper session persistence exposes user data or bypasses security checks.
  - *Mitigation:* Use secure cookie attributes (HttpOnly, Secure), keep session lifetime short, validate session on backend, avoid sensitive state on single instance.

- **Exploit: Data exposure via misconfigured cloud storage (public buckets)**
  - *What:* Sensitive data in public S3 buckets or open endpoints accessible from internet.
  - *Mitigation:* Enforce least-privilege IAM, block public ACLs at org level, enable bucket encryption, use monitoring (CloudTrail/Macie) and alerting for policy violations.


## 5) ASCII Diagram — Defense-in-Depth × Zero-Trust Stack

            ┌─────────────────────────────────────────────┐
            │                 Users / Devices             │
            │  MFA · Posture Check · SSO · IAM            │
            └─────────────────────────────────────────────┘
                               │
                      [Zero-Trust Policy Engine]
                               │
          ┌─────────────────────────────────────────────┐
          │         VPN / ZTNA / Forward Proxy          │
          │  → outbound control · traffic anonymization │
          └─────────────────────────────────────────────┘
                               │
          ┌─────────────────────────────────────────────┐
          │          Edge Firewall / WAF Layer          │
          │  → inbound filtering · anti-DDoS            │
          └─────────────────────────────────────────────┘
                               │
          ┌─────────────────────────────────────────────┐
          │    Load Balancer (L4/L7) + Reverse Proxy    │
          │  → TLS termination · content routing · WAF   │
          └─────────────────────────────────────────────┘
                               │
          ┌─────────────────────────────────────────────┐
          │     IDS / IPS / SIEM · Continuous Audit     │
          │  → anomaly detection · alert correlation    │
          └─────────────────────────────────────────────┘
                               │
          ┌─────────────────────────────────────────────┐
          │        Application & API Gateway Tier       │
          │  → validate requests · enforce RBAC         │
          └─────────────────────────────────────────────┘
                               │
          ┌─────────────────────────────────────────────┐
          │          Database / Storage Layer           │
          │  → encrypt data at rest (KMS) · DLP rules   │
          └─────────────────────────────────────────────┘
                               │
          ┌─────────────────────────────────────────────┐
          │            Logging / Monitoring             │
          │  → CloudWatch · GuardDuty · SIEM ingest     │
          └─────────────────────────────────────────────┘

Notes:
- Every arrow = authenticated + encrypted channel.
- All access paths go through policy evaluation before resource access.
- Continuous telemetry flows upward to the SIEM for visibility.


## 6) Reflection

**What clicked:**  
Layered security finally makes sense when viewed as traffic flowing through multiple verification gates. Zero-Trust isn’t another product—it’s a mindset: *verify every hop*.

**What to improve:**  
Need to practice mapping Zero-Trust controls to real AWS services (Control Tower, PrivateLink, IAM Identity Center). Next week I’ll reinforce this by diagramming an AWS-native Zero-Trust flow.
