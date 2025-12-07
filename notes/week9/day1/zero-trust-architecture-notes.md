# Zero Trust Architecture - Study Block Notes  

---

## Core Components

### Policy Engine (PE) - Decision Brain
- Evaluates identity, risk, device posture, behavior, and context.
- Produces verdicts: allow, deny, or step-up authentication.
- Represents the thinking and judging layer.

**Analogy:** Immigration officer reviewing documents.

---

### Policy Administrator (PA) - Signalling Layer
- Converts PE decisions into actionable enforcement.
- Issues tokens, revokes access, configures gateways, triggers MFA.
- Bridges decision to execution.

**Analogy:** Authority system that tells gates to open or close.

---

### Policy Enforcement Point (PEP) - Execution Gate
- Intercepts requests and applies allow/deny in real time.
- Enforces policy decisions.
- Generates telemetry for ongoing evaluation.

**Analogy:** The airport turnstile that opens only if cleared.

---

## Correct Zero Trust Flow (Operational Sequence)

Request → PEP intercepts
→ PA signals/query
→ PE evaluates and decides
→ PA delivers instruction
→ PEP enforces

**Compression:** The gate sees traffic first, the brain decides second.

---

## Where Zero Trust Breaks in Cloud

- Implicit trust between cloud services
- Over-privileged IAM roles bypassing evaluation layers
- Long lived tokens creating static trust
- Internal network zones assumed safe

**Core Insight:** Zero Trust fails wherever trust is assumed instead of continuously verified.

---

## Key Principle Contrast

### Perimeter Security
Authenticate once, trust permanently.

### Zero Trust
Authenticate always, evaluate continuously.

---

## Corrected Misconceptions

- Zero Trust is not password schedules; it is continuous re-validation.
- The Policy Engine is not the first component hit; the PEP intercepts first.
- Decision authority (PE) is distinct from physical enforcement (PEP).

---

## Quick Lookup Table

| Component | Role | Analogy |
|----------|------|---------|
| PE | Decision engine | Immigration officer |
| PA | Instruction layer | System instructing gate |
| PEP | Enforcement | Turnstile opening/closing |

---

## Cloud Mapping Examples

- PE = IAM policy evaluation, Azure Conditional Access
- PA = AWS STS issuing temporary credentials
- PEP = API gateway, firewall, reverse proxy, service mesh edge

---

## Synthesis

Zero Trust = continuous brain + signalling + gate enforcement loop.

Any disruption or static trust path becomes an attack surface.

---
