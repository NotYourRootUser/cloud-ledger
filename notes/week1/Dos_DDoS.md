# DoS / DDoS Notes (Security+)

- **What it is:** Attack that overwhelms resources. DoS = single source, DDoS = many sources (botnet).

## Common Types
- SYN flood → incomplete TCP handshakes.
- Amplification (DNS/NTP) → small request, huge reply.
- App-layer flood → HTTP requests overload app.
- Volumetric → bandwidth floods.

## Detection
- Traffic/CPU/memory spikes.
- Many incomplete SYN handshakes.
- IDS/IPS alerts (amplification).
- CDN/DDoS provider reports.

## CIA Impact
- **Availability:** High
- **Integrity:** Low
- **Confidentiality:** Low

## Mitigation
- Rate limiting + SYN cookies.
- CDNs / scrubbing services (Cloudflare, AWS Shield).
- IPS anomaly detection.
- Incident response playbooks.

## Tool
- Cloudflare/AWS Shield (defense).
- Snort/Suricata (detection).

## Analogy
- DoS = one prank caller keeps line busy.  
- DDoS = thousands call at once.
