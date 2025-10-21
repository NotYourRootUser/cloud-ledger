# Reverse – Domain 4.1

## Topic: Segmentation
**Questions**
- What happens if I connect all subnets together?
- Which attacks become easier in a flat network?
- Can segmentation ever hurt performance or security?

**Reasoning**
- The entire network becomes one large attack surface.
- In a flat network, attackers can move laterally with ease.
- Segmentation increases control but adds complexity and can reduce performance.

---

## Topic: Zero Trust
**Questions**
- If every device must authenticate, how do we balance usability?
- What does "never trust, always verify" not mean?
- Could Zero Trust fail if identity systems go down?

**Reasoning**
- Single sign on and adaptive authentication help balance authentication and usability.
- "Never trust, always verify" does not mean denying access after verification or removing pragmatic exceptions.
- If identity systems fail, local enforcement and segmentation should still limit exposure, but availability and recovery plans for identity services are required.

---

## Topic: Defense in Depth
**Questions**
- Why do redundant layers still matter if one control seems perfect?
- What is the downside of too many layers?

**Reasoning**
- Every control can fail; redundancy ensures that one breach does not collapse the whole defense.
- Excessive layering adds latency and complexity, increases the chance of misconfiguration, and can create a false sense of security.

---

## Topic: Routing and Wireless
**Questions**
- If BGP leaks occur, what chain reaction follows?
- Why might an open guest Wi-Fi network still be acceptable in a Zero Trust model?

**Reasoning**
- A BGP leak can reroute traffic to unintended AS paths where traffic may be intercepted, monitored, or modified.
- A guest Wi-Fi can be acceptable if it is fully isolated from production networks, rate limited, monitored, and subject to strict access controls.

---

## Topic: VPNs
**Questions**
- If split tunneling is risky, why do companies still allow it?
- When does a VPN reduce visibility for defenders?

**Reasoning**
- Companies allow split tunneling to save bandwidth and improve user performance; it is a tradeoff that must be managed.
- Full-tunnel VPNs can reduce visibility into endpoint-originated traffic for defenders because traffic is encapsulated and telemetry may not reach local monitoring tools.

---

## Topic: Firewalls and Bastions
**Questions**
- When does stateful inspection fail?
- How could a bastion itself become an attack vector?

**Reasoning**
- Stateful inspection can fail with encrypted, fragmented, or protocol-obfuscating traffic that the device cannot track effectively.
- A bastion can become an attack vector via misconfiguration, excessive privileges, unpatched software, or insufficient access controls and logging.
