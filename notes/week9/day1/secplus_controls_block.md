# Security Controls - Block Notes

## Six Control Families

### Preventive
Stops unwanted actions before they occur.  
Examples: MFA, firewalls, network segmentation, access control lists.

### Detective
Identifies violations or suspicious behavior during or after an event.  
Examples: logging, SIEM alerts, IDS, audit trails.

### Corrective
Restores systems or data after a failure or compromise.  
Examples: backups, patching, incident response runbooks.

### Deterrent
Discourages malicious behavior by increasing perceived risk.  
Examples: warning banners, cameras, visible guards, compliance penalties.

### Directive
Guides and mandates correct behavior through rules and expectations.  
Examples: policies, SOPs, security training, acceptable use policies.

### Compensating
Alternate controls used when preferred controls are not feasible.  
Examples: manual reviews substituting automation, MFA compensating for weak passwords.

---

## Interaction Model

Preventive tries to **stop**.
Detective tries to **see**.
Corrective tries to **fix**.
Deterrent tries to **discourage**.
Directive tries to **guide**.
Compensating tries to **replace** gaps.

---

## Insider Attack Lens

Insiders bypass:
- Preventive (they already have access)
- Deterrent (they may not care)

This shifts weight to:
- Detective (catch misuse)
- Corrective (recover damage)

---

## Exam Hooks

- “Which control **restores** state?” → Corrective  
- “Which control **tells people how to behave**?” → Directive  
- “Which control **reduces likelihood through fear**?” → Deterrent  
- “Which control is a **temporary workaround**?” → Compensating  
- “Which control **identifies activity**?” → Detective  
- “Which control **prevents incidents**?” → Preventive

---

## Mini Grid

| Control      | Purpose | Insider Weakness |
|--------------|---------|------------------|
| Preventive   | Stop    | Insider access bypass |
| Detective    | See     | Poor tuning or ignored alerts |
| Corrective   | Fix     | Slow recovery |
| Deterrent    | Discourage | Insider isn’t scared |
| Directive    | Guide   | Policy ignored |
| Compensating | Replace | Human fatigue or loopholes |

---

## One-Line Memory Script
“Stop → See → Fix → Scare → Guide → Replace.”


