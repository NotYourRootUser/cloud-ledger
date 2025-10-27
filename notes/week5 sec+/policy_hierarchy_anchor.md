# Policy Hierarchy Domain 5

## Definitions

- **Policy** is the mandatory rule that states _what_ must be done and _why_.
- A **Standard** is the minimum measurable requirement that supports the policy.
- **Procedure** is the step-by-step instructions that explain _how_ to meet the standard.
- **Guideline** - Recommended best practices that are optional and flexible.

## Analogys

**Driving laws model:**

- Policy = the **law** you must follow
- Standard = the **speed limits** enforcing minimum expectations
- Procedure = **driving instructions** that show how to comply
- Guideline = the **safety tips** that help you avoid mistakes

→ Policies lead → Standards enforce → Procedures instruct → Guidelines advise

## Visual

Stack structure:

Policy (top: the must)
↓
Standard (measurable thresholds)
↓
Procedure (step-by-step)
Guideline (advice on the side)

---

## Reverse / Challenging the Assumptions

### What if guidelines became enforced like policies?

- Users would be forced to follow advice that doesn’t fit every scenario.
- Creativity and rapid problem-solving would shrink under rigidity.
- Audit confusion: what is mandatory vs recommended becomes unclear → compliance disputes.

### What if there was no review cadence for policies?

- Policies would become outdated as technology and threats evolve.
- Weak or broken controls might stay in place for years without scrutiny.
- Regulators and auditors see stale policies as red flags → compliance failure.

### What if exceptions had no expiry or tracking?

- Orphaned permissions accumulate and create hidden attack paths.
- Insiders can retain elevated access long after the need is gone.
- Breach investigations stall because no one knows who approved what.

.These are failure modes when governance loses discipline.

---

## eXploit / Policy Hierarchy Exam Drill (8/8)

1️ A security analyst finds multiple conflicting onboarding procedures with different approval paths.  
Which governance issue does this indicate?  
**Answer: A - Procedures are not aligned to an authoritative standard**

2️ A new data retention standard requires 365-day log storage, but policy still says “appropriate period.”  
What risk does this mismatch create?  
**Answer: C - Inconsistent enforcement because the mandatory rule is unclear**

3️ A threat hunter wants to enforce guidelines as mandatory.  
What must happen first?  
**Answer: B - Rewrite guidelines into a policy or standard**

4️ Certificate rotation procedure updated, but standard still references the old method.  
What is the risk?  
**Answer: B - Procedures are outpacing policy and may break compliance**

5️ Engineers treat standards like optional advice.  
How to restore authority?  
**Answer: B - Re-issue standards with formal approval and attestations**

6️ Policy mandates encryption; standard requires AES-256; engineers use weaker ciphers.  
What fails?  
**Answer: B - Standard failure (minimum requirement not met)**

7️ MFA policy is mandatory, but procedures not updated yet.  
What should security enforce now?  
**Answer: B - Enforce MFA using any approved method**

8️ Junior admin removes dual-approval steps from a procedure.  
What prevents security weakening?  
**Answer: A - Standards cannot be overridden by procedures**

