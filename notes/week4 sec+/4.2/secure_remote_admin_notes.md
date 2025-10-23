# Secure Remote Administration Notes

## Anchor
Secure remote administration limits how admins connect to systems. 
SSH keys and certificates provide strong authentication without passwords. 
Jump servers (bastion hosts) centralize admin access, allowing auditing and control. 
AWS Systems Manager Session Manager achieves similar goals—secure sessions without open SSH ports.

## Reverse
Leaving SSH keys unprotected on laptops risks compromise if stolen. 
A compromised bastion can open the network to attackers. 
Always use short-lived credentials, MFA, and limit access to specific IPs or sessions.
