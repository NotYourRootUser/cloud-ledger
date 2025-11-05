# Zero Trust Governance 

## Zero Trust Flow v1
User → Bastion Host → Privileged Access Layer → Segmented VPCs

![Zero Trust Flow Diagram](zero_trust_flow_v1.png)

---

## Control Mapping Table

| Checkpoint | AWS Service / Control | Purpose |
|-------------|----------------------|----------|
| User Authentication | IAM Identity Center / MFA | Verify identity and enforce conditional access |
| Bastion Isolation | EC2 Bastion / SSM Session Manager | Secure admin plane access, no direct inbound SSH |
| Privileged Access Layer | IAM Roles / SCPs | Enforce least privilege and continuous verification |
| Segmented VPCs | VPC, Subnets, Security Groups, NACLs | Contain blast radius and restrict lateral movement |
| Monitoring | GuardDuty / CloudTrail / Config | Detect and audit anomalous behavior across layers |

---

## Governance Integration Notes

- **Zero Trust Principle:** Every session re-validated; no implicit trust.  
- **Admin Plane Isolation:** Management VPC only reachable via bastion or SSM.  
- **Break-Glass Account:** Offline MFA-protected root for emergencies only.  
- **SBOM Assurance:** CodeBuild/Inspector generate dependency inventories.  
- **Secure-by-Design:** Infrastructure-as-Code templates enforce encryption & tagging.  
- **Segmentation Enforcement:** Prod, Dev, and Test VPCs separated via TGW route filters.

---

## Compression Summary

**Zero Trust**  
Verify every identity, device, and request continuously.  
No implicit trust, context-aware access decisions.  
Defense extends across all network layers.  
→ *AWS Mapping:* IAM + SCPs + GuardDuty = policy + threat enforcement.

**Admin Plane Isolation**  
Separate management traffic from user/data plane.  
Restrict access via bastion or SSM sessions only.  
Prevents lateral pivot into control systems.  
→ *AWS Mapping:* Dedicated Admin VPC + PrivateLink = isolated control path.

**Break-Glass Account**  
Emergency high-privilege account for recovery.  
Stored offline, MFA-protected, tightly monitored.  
Used only during lockout or failure events.  
→ *AWS Mapping:* Root user with MFA + CloudTrail = controlled emergency access.

**SBOM**  
Full inventory of code components and dependencies.  
Tracks vulnerabilities and supply-chain risk.  
Requires continuous scanning and updates.  
→ *AWS Mapping:* CodeBuild + Inspector = automated SBOM generation.

**Secure-by-Design**  
Embed security from blueprint through deployment.  
Automate enforcement through code and reviews.  
Continuously validate configurations post-launch.  
→ *AWS Mapping:* IaC + Config Rules + SCPs = built-in secure defaults.

**Segmentation**  
Divide systems to limit blast radius and access scope.  
Each zone enforces least-privilege communication.  
Complexity managed through policy and tagging.  
→ *AWS Mapping:* VPCs + Security Groups + TGW filters = network segmentation.
