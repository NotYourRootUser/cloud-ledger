# security_controls_map.md

A compact map linking **control types**, **CIA**, **AAA**, **Zero Trust**, and **crypto basics** using only the foundations covered so far.

---

## 1. Control Types Overview

| Control Type       | Description                                      | Example                                      |
|--------------------|--------------------------------------------------|----------------------------------------------|
| Administrative     | Policies, rules, procedures, training            | Security policy, onboarding, AUP             |
| Technical (Logical)| Technology-based safeguards                      | MFA, IAM, TLS, full-disk encryption          |
| Physical           | Tangible protections for facilities & hardware   | Locks, CCTV, guards, biometrics, cages       |

Use this as your base classification layer for every control.

---

## 2. CIA Triad → Controls Mapping

### 2.1 Confidentiality

**Goal:** Prevent unauthorized access to data.

**Typical Controls:**

- **Technical**
  - Encryption (at rest & in transit)
  - IAM (roles, groups, policies)
  - MFA
  - Network segmentation, VLANs, security groups
- **Administrative**
  - Data classification policy
  - Acceptable use & access control policies
  - Security awareness training (phishing, sharing data)
- **Physical**
  - Locked server rooms
  - Visitor badges
  - Clean desk policy enforcement

---

### 2.2 Integrity

**Goal:** Ensure data is accurate, unaltered, and trustworthy.

**Typical Controls:**

- **Technical**
  - Hashing for file/backup verification
  - Digital signatures
  - Version control
  - Input validation
- **Administrative**
  - Change management procedures
  - Separation of duties
- **Physical**
  - Controlled access to wiring closets, servers (prevent tampering)

---

### 2.3 Availability

**Goal:** Ensure systems and data are accessible when needed.

**Typical Controls:**

- **Technical**
  - Redundant power, RAID, clustering
  - Backups and tested restores
  - DoS protection and rate limiting
- **Administrative**
  - Disaster recovery (DR) plan
  - Business continuity procedures
- **Physical**
  - Cooling, fire suppression
  - Physical protection of power/network gear

---

## 3. AAA Mapping (Authentication, Authorization, Accounting)

### 3.1 Authentication — "Who are you?"

**Examples (Technical Controls):**

- Passwords + MFA
- Biometrics
- Smart cards
- SSO/IdP (e.g., corporate login portals)

**Links:**
- Supports **Confidentiality** (only valid identities gain access).

---

### 3.2 Authorization — "What can you do?"

**Examples (Technical Controls):**

- Role-Based Access Control (RBAC)
- Least privilege on IAM roles/policies
- Network ACLs & firewall rules

**Links:**
- Protects **Confidentiality** and **Integrity** by limiting actions.

---

### 3.3 Accounting — "What did you do?"

**Examples (Technical Controls):**

- System, application, and access logs
- Admin action logging
- SIEM correlations

**Links:**
- Supports investigations, non-repudiation, and verification of **Integrity**.

---

## 4. Zero Trust Mapping

**Core Principle:** *Never trust, always verify.*

Key implementations (within covered scope):

- Enforce **strong Authentication** (MFA everywhere).
- Use **least privilege Authorization** (minimal access).
- **Microsegmentation**: re-authenticate between network zones.
- Continuous **Accounting**: monitor sessions, analyze anomalies.

**Primary CIA impact:**  
- Strengthens **Confidentiality** (harder for unauthorized access).
- Also improves **Integrity** (fewer users can modify critical assets).
- Must be engineered not to harm **Availability** (avoid auth bottlenecks).

---

## 5. Cryptography Basics Mapping

### 5.1 Encryption

**What:** Transforms plaintext → ciphertext using keys.

**Protects:** **Confidentiality**

**Examples:**

- Full-disk encryption (laptops, servers)
- Database encryption
- TLS for data in transit

---

### 5.2 Hashing

**What:** One-way function; same input → same output; changes reveal tampering.

**Protects:** **Integrity**

**Examples:**

- Verifying downloaded files
- Checking backup integrity
- Password storage (hash + salt)

---

### 5.3 Digital Signatures

**What:** Hash + asymmetric crypto to verify sender + integrity.

**Protects:**

- **Integrity** (detects modification)
- **Authentication** (proves who signed)
- Supports **non-repudiation**

---

## 6. Fast Lookup Table

| Concept          | Primary Pillar | Primary Control Types         | Example                                      |
|-----------------|----------------|-------------------------------|----------------------------------------------|
| MFA             | Confidentiality | Technical                     | User + OTP for VPN / portal                  |
| FDE (disk enc)  | Confidentiality | Technical                     | Encrypted laptop HDD/SSD                     |
| Hash check      | Integrity       | Technical                     | Compare file hash before/after transfer      |
| Backups + RAID  | Availability    | Technical (+ Admin)           | Nightly backups, RAID 1/5/10                 |
| CCTV + locks    | C/I/A (support) | Physical                      | Monitored server room                        |
| Least privilege | C/I             | Technical (+ Admin)           | Tight IAM roles, app permissions             |
| Logging (AAA)   | Integrity       | Technical                     | Admin action logs to SIEM                    |
| Segmentation    | Confidentiality | Technical                     | Separate prod/dev networks, ACLs             |
| Zero Trust MFA  | Confidentiality | Technical                     | Re-auth for sensitive apps                   |

---

Use this file as a **reference map** during Security+ Domain 1 study and scenario questions:
1. Identify which **pillar** is impacted.
2. Identify which **control type** applies.
3. Anchor it to **AAA / Zero Trust / Crypto** where relevant.

