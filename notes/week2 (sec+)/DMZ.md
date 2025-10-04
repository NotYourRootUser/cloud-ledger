# DMZ Notes (Security+)

- **What it is:** Demilitarized Zone — network segment that exposes public-facing services (web, mail, DNS) to the internet while isolating the internal network.

## Placement & architecture
- Classic setup: Internet → external firewall → DMZ → internal firewall → internal network.
- Services in DMZ are reachable from internet but have restricted access to internal resources.

## Detection / How issues show up
- Compromise of a DMZ host (detected via IDS/HIPS or unusual outbound connections to internal hosts).
- Excessive failed auth attempts on DMZ services.
- Traffic from DMZ to internal network that violates ACLs (indicates possible pivot).

## CIA Impact
- **Availability:** High for public services (need to stay available).
- **Confidentiality / Integrity:** Medium/Low for internal network (DMZ is hardened to limit internal exposure).

## Practical mitigations / Best practice
- Harden DMZ hosts (minimal services, patching, host-based protections).
- Use application-layer proxies and WAFs for web services.
- Strict firewall rules: DMZ can talk to internal hosts only on necessary ports and via jump hosts or application gateways.
- Monitor DMZ closely with IDS/EDR and limit management access (out-of-band or jump-host).
- Regularly patch and rotate keys/certs; use segmented backups.

## One representative design element
- Dual-firewall DMZ (external + internal) or single firewall with separate interfaces — choose based on risk and budget.

## Quick analogy
- DMZ = the building foyer where visitors wait — they can interact with public staff but they don’t get direct access to the offices inside unless escorted.
