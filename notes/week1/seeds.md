# Network & Web Attack Notes

## MITM — Man-in-the-Middle
**Definition**  
Interception of communication between two parties that allows an attacker to read and/or modify traffic.

**Analogy**  
Imagine two people having a conversation and someone sits between them — either actively changing what they say (active) or just listening in (passive).

**Visual (ASCII)**  
`Party ===== Attacker ===== Party`

---

## SQLi — SQL Injection
**Definition**  
Injection of malicious SQL into an application's input or query so the database executes unintended commands, allowing data to be read, modified, or deleted.

**Mitigation**  
- Use parameterized queries / prepared statements so user input is treated strictly as data (never concatenate user input into SQL).
- Apply least-privilege database accounts and input allowlists/validation.

**Detection**  
- Monitor DB query logs and WAF/IDS alerts for anomalous or SQL-like payloads and error patterns (e.g., `' OR '1'='1'`, `UNION SELECT`, unexpected syntax errors).

---

## XSS — Cross-Site Scripting
**Definition**  
Injection of malicious scripts into web pages viewed by users, allowing attackers to run code in the victim’s browser (cookie theft, DOM manipulation, session hijack).

**Mitigation**  
- Sanitize and contextually encode user input/output (HTML, attribute, JS, URL contexts).
- Implement Content Security Policy (CSP).
- Mark cookies `HttpOnly` and `Secure`.

**Detection**  
- Monitor IDS/WAF logs for suspicious `<script>` tags or unusual parameter values in HTTP requests.
- Watch for client-side errors or anomalous referrer patterns.

---

## DoS / DDoS — Denial of Service
**Definition**  
Attacks that overwhelm a target’s resources or network with traffic to deny service to legitimate users.  
- **DoS** = single source.  
- **DDoS** = many distributed sources.

---

## Vulnerability Scan
**Definition**  
Automated scanning of systems, applications, or networks to identify known weaknesses, misconfigurations, or missing patches.

**Types**  
- **Credentialed scan:** uses valid credentials for a deeper view of system/configuration.  
- **Non-credentialed scan:** no credentials; limited to external surface.

---

## Buffer Overflow
**Definition**  
An attack that sends more data to a memory buffer than it can hold, causing crashes or potentially allowing an attacker to execute arbitrary code.
