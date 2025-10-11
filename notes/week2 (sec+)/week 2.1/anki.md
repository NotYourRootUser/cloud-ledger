Front: What is the main purpose of a bastion host (jump box)?
Back: To provide a single hardened entry point for administrators to access private systems securely, isolating management traffic from the internet.

Front: Where should a bastion host be placed in a cloud network?
Back: In a public subnet with strict inbound rules; it connects to private subnets that contain internal instances.

Front: Why use AWS SSM Session Manager instead of SSH?
Back: It removes key management and direct network exposure, allowing audited, keyless, browser-based or CLI sessions.

Front: What’s the difference between a firewall and a WAF?
Back: A firewall filters network packets by IP/port (Layer 3–4); a WAF filters HTTP/S traffic by content and behavior (Layer 7).

Front: Where is a DMZ placed in a typical network design?
Back: Between the external and internal firewalls; it hosts public-facing services like web or mail servers.

Front: How does network segmentation improve security?
Back: It limits lateral movement by isolating systems into VLANs or subnets with ACLs controlling traffic between them.

Front: What is the rule order in ACL evaluation?
Back: Top-down; first match wins, so deny/allow order determines final traffic behavior.

Front: What’s the function of NAT in security architecture?
Back: It hides internal IP addresses, translating private to public, reducing attack surface and enabling outbound access.

Front: What is a VPN used for?
Back: To create an encrypted tunnel for secure remote access or site-to-site communication across untrusted networks.

Front: How do IDS and IPS differ?
Back: IDS detects and alerts on suspicious traffic; IPS detects and automatically blocks or drops malicious traffic.

Front: Where should IDS/IPS be placed in a network?
Back: IDS before the internal firewall for visibility; IPS inline between trusted zones to block real-time threats.

Front: What’s the key difference between Security Groups and NACLs in AWS?
Back: Security Groups are stateful and instance-level; NACLs are stateless and subnet-level.

Front: How does a load balancer improve security and reliability?
Back: It distributes traffic evenly, hides internal servers, and can integrate with WAF or TLS termination for protection.

Front: What is the purpose of a proxy server?
Back: It intermediates requests, masking client identity, enforcing content policies, and caching traffic.

Front: What principle defines the Zero-Trust model?
Back: Never trust, always verify — continuous authentication, authorization, and least-privilege enforcement.

Front: What is defense-in-depth?
Back: Layering multiple security controls (technical, administrative, physical) to ensure no single point of failure.

Front: What AWS service can help centralize logging and monitoring of network traffic?
Back: Amazon CloudWatch or GuardDuty integrated with VPC Flow Logs.

Front: Why deploy bastion hosts across multiple Availability Zones?
Back: For high availability — if one AZ fails, another bastion remains accessible for admin operations.

Front: What’s the main benefit of disabling public IPs on private EC2 instances?
Back: Prevents direct internet access, reducing exposure and forcing all access through secure gateways like bastions or VPNs.

Front: How do IAM policies reinforce architecture security?
Back: They enforce least privilege and restrict who can modify or access network components.

Front: What is a common pitfall when configuring ACLs?
Back: Placing an allow rule before a deny rule that should take precedence, unintentionally permitting unwanted traffic.

Front: What does “stateful” mean in firewall behavior?
Back: It tracks connection states and automatically allows return traffic; stateless devices require explicit rules both ways.

Front: Why log administrative access on bastion hosts?
Back: For accountability, audit trails, and incident response to detect unauthorized or risky activity.

Front: What is the difference between availability and redundancy?
Back: Availability ensures continuous operation; redundancy provides backups or duplicates to support availability.

Front: Why is subnet isolation critical in multi-tier design?
Back: It confines compromise to one layer (web, app, DB) and enforces control boundaries between trust zones.

Front: What’s the primary purpose of a DMZ firewall rule set?
Back: To tightly control inbound access to public services and restrict outbound flow to internal networks.

Front: What architectural control enforces compartmentalization between tenants or environments?
Back: Network segmentation using VLANs, VPCs, or micro-segmentation policies.

Front: What is the security risk of using shared jump boxes without proper IAM?
Back: Loss of accountability and potential privilege escalation — sessions become untraceable.

Front: How does using an NLB in front of bastion hosts enhance resilience?
Back: It provides fault tolerance, distributes SSH/RDP traffic, and ensures consistent access across AZs.

Front: Why combine VPN access with bastion hosts?
Back: VPN provides encrypted tunnels; bastions add an extra layer of authentication and logging before private access.

Front: What layer do WAFs operate on in the OSI model?
Back: Layer 7 (Application layer).

Front: What concept ensures users have only the access they need to perform their job?
Back: Principle of least privilege.

Front: What is the benefit of infrastructure-as-code for security architecture?
Back: Repeatable, version-controlled deployments that reduce misconfiguration risk.

Front: What is the advantage of using parameter stores for credentials?
Back: Keeps secrets out of code and maintains encrypted, controlled access.

Front: How does a proxy cache improve both performance and security?
Back: It serves cached content to reduce load while filtering or blocking malicious traffic patterns.

Front: What does a misconfigured ACL risk causing?
Back: Accidental exposure of private resources or unintended service outages.

Front: Why monitor VPC Flow Logs?
Back: To detect abnormal connections, troubleshoot traffic paths, and identify unauthorized access attempts.

Front: What’s the difference between a forward proxy and a reverse proxy?
Back: Forward proxy sits before clients to control outbound access; reverse proxy sits before servers to manage inbound requests.

Front: How does encryption in transit differ from encryption at rest?
Back: In transit protects data over the network; at rest protects stored data on disks or backups.

Front: Why is least privilege applied to security groups important?
Back: Reduces attack surface by allowing only the minimal required ports and protocols.

Front: What is a jump host’s main audit advantage?
Back: Centralizes all administrative access logs for analysis and compliance.

Front: Why are multi-AZ bastion deployments considered best practice?
Back: They ensure continuous admin access even during AZ outages and meet high-availability requirements.
