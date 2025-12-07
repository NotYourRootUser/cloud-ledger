CIA protects systems, AAA protects identities, and Non-Repudiation proves actions really occurred.

Confidentiality = keeping data secret by limiting access (like privacy curtains).  
Integrity = ensuring data cannot be changed improperly (like tamper seals).  
Availability = keeping systems usable when needed (like room lights staying powered).

Authentication = proving identity (like showing an ID).  
Authorization = deciding what an identity may do (like room access zones).  
Accounting = recording what happened so it can be examined (like CCTV logs).

Non-repudiation = preventing someone from denying their actions later by binding identity to logs with integrity controls (like signed delivery receipts).

CIA underpins AAA because if integrity fails, auth logs cannot be trusted; if availability fails, AAA cannot verify identity; if confidentiality fails, credentials leak.  
AAA operationalizes CIA at the human layer: who you are, what you can do, and what is traced.  
Non-repudiation depends on AAA + integrity: logs tied to identities, protected from tampering, and retrievable.

Where AAA fails even if CIA seems fine:
– a rogue admin deletes logs, so accountability collapses  
– MFA verifies identity but weak logging lets the attacker deny actions  
– availability outage means no auth enforcement, so anyone bypasses controls  
– authorization misconfigured gives excessive privilege

Simple rule: CIA is trust in systems, AAA is trust in people, Non-Repudiation is proof of trust.

All three move like a chain:
CIA → makes AAA meaningful → enables evidence → makes non-repudiation possible.

If any link breaks, the whole security model weakens.

