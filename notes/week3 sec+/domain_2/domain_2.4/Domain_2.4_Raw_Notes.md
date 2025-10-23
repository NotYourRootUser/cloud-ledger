# Domain 2.4 Notes — Common Vulnerabilities (Raw)

misconfigurations -> default creds, open admin ports, public S3, overly-permissive IAM, insecure CORS
- memory: "unlocked doors in digital houses"
- fixes: disable public, restrict by IP/VPC, least-privilege, rotate creds, config review

software vulns -> bad code lets attacker execute / alter / crash
- sql injection -> ' OR '1'='1 -> parameterized queries, input validation
- xss -> attacker runs script in victim browser -> output encoding, CSP
- buffer overflow -> extra bytes overwrite memory -> bounds checks, safe libs
- race condition -> timing bug gives wrong state -> atomic ops, locks
- deserialization -> rebuilding untrusted data -> validate, use safe libs
- insecure deserialization -> crafted serialized object -> possible RCE
- memory: "bad input breaks good logic"

device / iot / ot -> outdated firmware, no patch, hard-coded keys, no segmentation
- examples: old routers, PLCs, cameras
- fixes: firmware updates, network segmentation, disable unused services
- memory: "tiny computers, giant holes"

vuln classes -> CVE ID (catalog), CVSS (0-10 severity)
- base metrics: AV, AC, PR, UI, S, C, I, A
- use CVSS to prioritize patches
- memory: "score the hurt before the hack"

detection signals -> short list to check quickly
- public S3 -> CloudTrail GetObject from unknown IP, S3 access logs, GuardDuty finding
- sql injection -> surge in DB errors, anomalous queries, WAF logs
- xss -> unexpected script in responses, user reports, CSP violations
- buffer overflow -> app crash, core dump, abnormal restarts, EDR alerts
- insecure deserialization -> unexpected object processing logs, exceptions, stack traces
- iot beaconing -> NetFlow/IDS shows regular outbound to rare IPs
- CVE advisory -> vendor bulletin, threat intel feed, exploit PoC in public

quick lab checklist (nmap + notes)
- run: nmap -sS -sV -O <target_ip>
- capture output, sanitize, paste into nmap_lab.md
- map ports -> services -> known CVEs -> fix notes

nmap example table (raw)
| port | service | risk | example cve | fix |
|------|---------|------|-------------|-----|
| 22   | ssh     | brute force | - | key auth, fail2ban |
| 80   | http    | path traversal | CVE-2021-41773 | patch apache |
| 3389 | rdp     | remote exploit | CVE-2019-0708 | disable/limit access |

anki prompts (make 5)
- Q: What is a public S3 bucket and how to detect it? -> A: Public S3 is... detect via CloudTrail GetObject, block public access
- Q: Give one sign of SQL injection -> A: spike in DB errors / odd queries
- Q: What does CVSS AV stand for? -> A: Attack Vector
- Q: Name one fix for insecure deserialization -> A: validate inputs, use integrity checks
- Q: IoT beaconing detection -> A: NetFlow shows periodic outbound to unknown IPs

final quick anchors
- misconfigs invite
- software flaws enable
- iot expands surface
- cvss quantifies urgency

End of notes
