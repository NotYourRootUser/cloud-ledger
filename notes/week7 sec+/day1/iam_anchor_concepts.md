# IAM Anchor Concepts

**Principle of Least Privilege**  
Grant only the exact permissions required to perform a task. Reduce scope, avoid broad roles, and prefer narrowly scoped policies or role assumptions.

**Root Account**  
Account owner identity used only for billing, account recovery, or initial organization setup. Lock it down, enable MFA, and never use it for daily administration.

**MFA (Multi-Factor Authentication)**  
Requires an additional factor—such as a hardware token or authenticator app—to prevent access even if credentials are compromised.

**SCP (Service Control Policy)**  
Organization-level guardrails that cap what actions can be performed in member accounts. SCPs restrict but do not grant permissions. Explicit Deny in an SCP overrides any Allow in IAM.

**IAM Control Stack (Compression Summary)**  
Root = governance layer  
Organizations + SCPs = global guardrails  
Accounts = operational boundary (CloudTrail + Config active)  
IAM users/roles = operational identities  
MFA = identity hardening  
Principle = apply least privilege, prefer roles for automation, lock the root.

