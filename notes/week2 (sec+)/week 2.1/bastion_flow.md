# Bastion Host / Jump Box Flow + High Availability

A bastion host, also known as a jump box, is the single secure doorway into a private network.  
In AWS it usually sits in a **public subnet**, where administrators connect to it through SSH or RDP.  
From the bastion, they can reach private EC2 instances that have no public IPs.  
This design limits exposure by forcing all admin access through one monitored point instead of opening every instance to the internet.

The bastion is locked down as tightly as possible.  
Inbound rules only allow connections from trusted IPs or a company VPN.  
Outbound rules are restricted so it can reach only the internal subnets that actually need management.  
Password logins are turned off; admins use SSH keys or, ideally, **AWS Systems Manager Session Manager**, which removes the need for direct network access or key files altogether.

Every session should be logged and monitored.  
**CloudWatch**, **GuardDuty**, and **CloudTrail** capture who connected, when, and what actions were taken.  
Access is granted through IAM roles with the principle of least privilege, and MFA is required for all admin accounts.

To keep the system reliable, bastion hosts are often deployed in **two Availability Zones** for high availability.  
They’re placed in an **Auto Scaling Group** behind a **Network Load Balancer**, so if one fails, another replaces it automatically.  
Configuration details such as startup scripts or connection policies are stored in **Parameter Store** or **Secrets Manager** to protect credentials and maintain consistency.

In short, the bastion host acts as a guarded checkpoint — one hardened EC2 instance that enforces controlled entry into private resources.  
It’s a critical piece of a **Zero-Trust** cloud design, combining isolation, auditing, and resilience to keep administrative access secure and accountable.
