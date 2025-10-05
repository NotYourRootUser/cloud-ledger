# IDS vs IPS vs WAF — Blue Team One-Pager (Psychology Lens)

## 1️ Definitions

| Control | Function | Placement | Key Phrase |
|----------|-----------|------------|-------------|
| **IDS** | Detects suspicious or malicious traffic and generates alerts. | Out-of-band (mirror port) | “Sees everything, blocks nothing.” |
| **IPS** | Blocks or drops packets inline based on signatures or behavior. | Inline between network segments | “Gatekeeper that enforces rules.” |
| **WAF** | Filters HTTP/S traffic at Layer 7 to stop SQLi, XSS, and input-based attacks. | In front of web servers / load balancer | “Web-layer bouncer.” |

---

## 2️ Control Triangle Mapping (Control | Detect | Contain)

- **Control (Prevent):** IPS + WAF — actively block malicious traffic.  
- **Detect:** IDS — observe, alert, and feed SIEM analytics.  
- **Contain:** Segmentation / Isolation / Sandbox — limit blast radius once detected.

---

## 3️ Scenario Logic — HTTP POST Spike → 500 Errors

- Likely cause → malicious input (SQLi / command injection).  
- **Check first:** Prevent control → tune WAF rules / enable blocking.  
- **If still firing:** Use IDS to correlate patterns.  
- **If host impacted:** Contain via segmentation or quarantine.

---

## 4️ Common Misconfig Tells

1. **WAF in Monitor-Only Mode** → False-positive fear / blame avoidance bias.  
2. **Outdated IDS/IPS Signatures** → Alert fatigue + maintenance neglect.  
3. **Over-broad ACLs or Security Groups** → Default-allow exposure.

---

## 5️ Psychology Lens Notes

- **Bias:** Familiarity + False Positive Aversion → teams prefer “visibility over protection.”  
- **Reframe:** Monitoring is temporary; true defense needs prevention with careful tuning.

---

## 6️ Key Sentence for Exam

> “IDS detects, IPS prevents, WAF filters inputs — together they create layered defense and reduce human bias toward monitor-only comfort.”
