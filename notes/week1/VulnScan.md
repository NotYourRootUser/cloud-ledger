# Vulnerability Scanning Notes (Security+)

- **What it is:** Automated tool that finds misconfigs/weaknesses. Common: Nessus, OpenVAS, Qualys.

## Detection / Output
- Reports list CVEs + CVSS scores.
- False positives are common.
- Scheduled scans find new issues after patches/changes.

## CIA Impact
- **Integrity:** Medium
- **Availability:** Medium
- **Confidentiality:** Medium  
(Depends on what vuln could be exploited.)

## Types
- Authenticated vs Unauthenticated.
- Active vs Passive.

## Common Findings
- Missing patches.
- Default creds.
- Weak TLS configs.
- Unnecessary open services.

## Mitigation / Process
- Validate + triage false positives.
- Prioritize by CVSS + business criticality.
- Patch, harden, rotate creds.
- Re-scan to confirm fixes.
- Combine with pen testing.

## Limitations
- Can’t detect zero-days or logic flaws.
- Auth scans need creds (security risk).
- Active scans can disrupt fragile systems.

## Tool
- Nessus (industry standard).

## Analogy
- Like a medical checkup: finds symptoms but not the full disease — needs a specialist (pen tester) to confirm.
