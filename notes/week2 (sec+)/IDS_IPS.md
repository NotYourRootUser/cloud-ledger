# IDS / IPS Notes (Security+)

- **What it is:** Systems that detect (IDS) and optionally block (IPS) malicious activity by inspecting traffic or host activity.

## Types
- NIDS (Network-based) vs HIDS (Host-based).
- Detection methods: signature-based vs anomaly/behavior-based.
- Placement: IDS typically out-of-band; IPS inline.

## Detection / How issues show up
- IDS alerts for known signatures or anomaly thresholds.
- High false-positive rates that require tuning.
- IPS logs showing dropped connections or blocked IPs.
- SIEM correlates IDS/IPS alerts with other telemetry for triage.

## CIA Impact
- **Availability:** Medium (IPS can block legit traffic if misconfigured).
- **Confidentiality/Integrity:** Medium (detects/prevents attacks that would impact CIA).

## Practical mitigations / Best practice
- Tune signatures and baselines to reduce false positives.
- Use layered detection (HIDS + NIDS + endpoint AV + EDR).
- Place inline IPS carefully (fail-open vs fail-closed decision).
- Regularly update signature feeds and maintain a tuning/exception process.
- Integrate alerts with SIEM and incident response playbooks.

## One representative tool
- **Snort / Suricata / OSSEC (HIDS)** for detection; vendors like Palo Alto and Cisco have integrated IPS features.

## Quick analogy
- IDS = CCTV camera that records and alerts security.  
- IPS = the camera plus a guard who can step in and stop the attacker.
