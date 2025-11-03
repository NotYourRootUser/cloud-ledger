# AWS Shared Responsibility Model

| Layer | AWS Responsibility | Customer Responsibility | Example Control |
|--------|--------------------|--------------------------|----------------|
| Infrastructure | Physical security, networking | None (abstracted) | CCTV, data center badges |
| Virtualization | Hypervisor patching | Instance OS patching | EC2 host vs guest updates |
| Data | Encryption services (KMS) | Key management & access policies | S3 SSE-KMS, IAM policy |
| Applications | Managed service uptime | App configuration, code security | RDS, Lambda env vars |
| Governance | Compliance frameworks | IAM, audit logging | CloudTrail, SCPs |
