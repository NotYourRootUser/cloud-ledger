# Domain 5.1 / Personnel Controls

## Separation of Duties (Anchor)
So its to **prevent** one person from **creating + approving + deploying** a risky change **alone**, like needing both keys to launch a nuke, no single actor can fire. So two key icons turning together → lock opens (dual-control)

---

## Enforcement Checks

CI/CD - **Approval gate**  
No one can push directly to prod.  
Require a **separate reviewer** for merge + deployment pipeline approval.

IaC - **Dual-control on privileged changes**  
If Terraform plan modifies security groups, IAM, KMS, or routing:  
Require **second approver** + automated **policy-as-code scan** (e.g., OPA/tfsec).

Change Control - **Peer + Authority separation**  
The **implementer ≠ approver**.  
Emergency changes require logged **post-review** and **dual sign-off** for rollback.
