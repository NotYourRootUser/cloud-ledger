# Domain 5.1 / Governance Foundations  
Charter • RACI • Authority to Act 

---

## Anchor -

### Charter
A formal document that grants the security team **authority**, **scope**, and an **executive sponsor** to enforce controls. Kind of like a **badge + warrant** empowering security to act even when others resist. When i think of Charter i picture a **sealed, signed authorization document**.  

---

### RACI Matrix
Clarifies who **does the work**, who **owns the outcome**, who **advises before**, and who **receives updates after**.

| Role | Meaning | Timing | Example |
|------|---------|--------|---------|
| Responsible | Executes the task | During | Security engineer applying controls |
| Accountable | **Owns** success or failure (only **one**) | Before/After | CISO reporting to leadership |
| Consulted | Expert input influencing action | Before | IAM specialist advising policy |
| Informed | Updated on progress/outcomes | After | Stakeholders receiving incident reports |

**Do • Own • Advise Before • Hear After** like football: players (R), coach (A), assistants (C), audience (I). I picture it as a **4-column table** with names locked in each role

---

### Authority to Act
The power for security to **enforce controls**, **halt risky actions**, and **escalate when needed,** like a **referee whistle** that immediately stops the game. I picture **red “SECURITY ONLY” door** with a keycard lock when I think of **authority to act.**

---

### Governance Integration 

| Control | Purpose | If Missing |
|---------|---------|------------|
| Charter | Establish mandate and support | Security ignored or bypassed |
| RACI | Clear accountability and roles | Confusion and stalled action |
| Authority to Act | Enforce and escalate decisions | Risk continues unchecked |

Security governance requires **clarity + power**.  
Advice without enforcement is ignored.

---

## Reverse // Insider Abuse and Governance Weak Points

### Q1 - What if the Responsible actor intentionally executes the task incorrectly?

*Impact:* Insider sabotage bypasses normal controls  
*Governance Fix:* SoD, peer review, immutable logs, rapid escalation empowered by Authority to Act

### Q2 - What if the person with Authority to Act accepts a bribe and deliberately sabotages enforcement?

*Impact:* A compromised enforcer turns controls into attack vectors; malicious changes can be hidden and escalations blocked.  
*Mitigations:* Dual-control for enforcement actions; independent oversight/internal audit; rotation and least-privilege for enforcement roles; regular attestation; tamper-evident external logs; anonymous whistleblower channel; periodic red-team integrity checks.

### Q3 - What if a Consulted subject-matter expert intentionally feeds false or misleading information before execution to steer outcomes?

*Impact:* Poisoned advice causes correct execution of incorrect plans, misconfigs, insecure workarounds, and deliberate failure modes.  
*Mitigations:* Cross-check inputs with independent review; require evidence-based recommendations; record decision rationale; limit consult scope; consult multiple SMEs for high-risk changes; enforce automated policy-as-code guards; run post-change canary validations and telemetry checks.

### Q4 - What if the person with Authority to Act instructs teams to ignore alerts?

*Impact:* Detection becomes blind by instruction; malicious activity can persist without escalation, and trust in governance erodes.  
*Mitigations:* Dual-approval for alert suppression; immutable alert streams to external SIEM; protected escalation path bypassing Authority; automated guardrails that still trigger response; audited suppression logs with oversight review.

### Q5 - What if an Informed stakeholder attempts to direct actions or override decisions based on the updates they receive?

*Impact:* Role boundaries collapse, decision-making authority shifts to someone without responsibility or expertise, causing misalignment, delays, or insecure outcomes.  
*Mitigations:* Enforce RACI boundaries in policy; require escalation through the Accountable role; restrict decision controls to Authorized roles; maintain audit trails showing who attempted to influence actions and how governance responded.

---

## eXploit / Escalation Flow

**Diagram (exported PNG):**  
![Escalation Flow](sandbox:/mnt/data/screenshot-2025-10-27_10-54-28.png)

### Flow summary
Detector → Notifier → IR Lead → Decision (Escalate? Severity / Scope / Compliance) → External Reporting  
Dashed bypass: Whistleblow (anonymous/protected) → Compliance / Hotline (Protected Channel)

### Evidence / SLA anchors
- Detector → Notifier: **Alert ID + timestamp + log reference**
- Notifier → IR Lead: **Ticket opened (ID) + triage notes (≤15m)**
- IR Lead → Decision Authority: **Severity report + containment status (≤30m ack)**
- Decision Authority → External Reporting: **Reg trigger? (72h breach reporting law)**
- Whistleblow bypass note: **Protected channel — anonymity required by policy**

### Mapping Questions
1. **Where can alerts die without a ticket or acknowledgment?**  
2. **Who can stall escalation by withholding severity or scope details?**

### Compression Sentences
3. **Delayed acknowledgment gives attackers quiet time to move laterally.**  
4. **If the decision authority is compromised, escalation collapses without bypass protections.**

