# Domain 4.3 Implement Secure Network Management

## Management Plane Segregation
Keep the management plane separate from user or data traffic. Use dedicated VLANs, subnets, or even physical networks (OOB - Out of Band). Limit access to admins and monitoring systems only.

Example: Use a management VLAN that only allows SSH or HTTPS from trusted IPs. Combine with jump hosts or VPNs.

**Recall**
- What is the purpose of separating management traffic?
- How could a single flat network create security risks?
- Which AWS component acts like an OOB network for management access?

---

## SNMP v3 SSH and API Security
Always prefer encrypted management protocols. Replace Telnet and SNMP v1/v2 with SNMP v3 and SSH. For APIs, enforce HTTPS and signed requests.

Example: Use SSH key-based authentication and disable password logins. When using APIs for SDN or IaC, store tokens securely.

**Recall**
- Why is SNMP v2 insecure?
- What key feature makes SNMP v3 safer?
- What happens if an API key is stored in plain text in a repo?

---

## Configuration Backup and Integrity Checks
Network configurations should be backed up automatically and verified for integrity. Use hashes or checksums to detect tampering.

Example: Use Git to version control switch configs or use AWS Config for tracking drift in cloud environments.

**Recall**
- Why is configuration integrity important?
- What is one benefit of storing configs in Git?
- What happens if backups are not encrypted?

---

## Centralized Logging and SIEM Integration
Send all network logs to a central location. Correlate events using a SIEM to detect patterns and anomalies.

Example: In AWS, use CloudWatch Logs and send them to Security Hub or GuardDuty for correlation.

**Recall**
- Why centralize logs?
- What risks come from leaving logs only on local devices?
- What type of data does a SIEM analyze?

---

## Certificate Management for Network Devices
Certificates prove identity and enable encryption. Use CA-signed certificates and automate renewals to prevent outages.

Example: Use AWS ACM or Let's Encrypt automation to renew device certificates regularly.

**Recall**
- What happens when a cert expires?
- How can automation reduce risk in certificate management?
- Why is using self-signed certificates risky in production?

---

## Secrets Management for Credentials and API Keys
Never hardcode passwords or API keys. Use a secrets manager to store and rotate them securely.

Example: AWS Secrets Manager or HashiCorp Vault can automatically rotate keys and limit access based on roles.

**Recall**
- Why is plaintext credential storage dangerous?
- How often should API keys be rotated?
- Which tool can automate secret rotation in AWS?

---

## Automation Safety and RBAC
Automation is powerful but risky if permissions are too broad. Use role-based access control (RBAC) and approval workflows to prevent misuse.

Example: In Terraform or Ansible, limit who can apply infrastructure changes and log all actions.

**Recall**
- How can automation cause harm without RBAC?
- Why log every automation action?
- What is the difference between RBAC and ABAC (attribute-based access control)?
