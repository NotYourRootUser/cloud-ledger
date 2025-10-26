# IDS vs IPS vs WAF 

## Summary
- **IDS** = Detects suspicious traffic; out-of-band; generates alerts only.  
- **IPS** = Inline; blocks or drops malicious packets; enforces prevention.  
- **WAF** = Layer 7 filter; stops input attacks (SQLi, XSS); protects web apps.

---

## Control Triangle Mapping
| Function | Tools | Purpose |
|-----------|--------|----------|
| **Control (Prevent)** | IPS, WAF | Actively block malicious traffic. |
| **Detect** | IDS | Observe and alert via logs or SIEM. |
| **Contain** | Segmentation, Isolation, Sandbox | Limit blast radius after detection. |

---

## Scenario - HTTP POST Spike → 500 Errors
- **Pattern:** Many large POST requests + 500 errors = input-based attack.  
- **Step 1:** Check *Prevent* control → tune WAF rules / enable blocking.  
- **Step 2:** If already blocking → verify *Detect* layer (IDS).  
- **Step 3:** If compromised → apply *Contain* (isolate web tier).

---

## Common Misconfig Tells
1. WAF left in *monitor-only* mode (fear of false positives).  
2. Outdated IDS/IPS signatures (alert fatigue).  
3. Over-broad ACLs or SGs (default-allow exposure).

---

## Psychology Lens
- Teams prefer “monitoring” over “blocking” to avoid blame (false positive bias).  
- Reframe: prevention with tuning = true security maturity.

---

## Exam Line
> IDS detects. IPS prevents. WAF filters inputs. Together they layer defense and offset human bias toward comfort.
