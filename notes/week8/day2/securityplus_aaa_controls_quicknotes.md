# Security+ Quick Notes Sheet
For AAA, Access Control Models, Authentication Methods, and Security Control Categories

## AAA Framework
Authentication: Verifies identity. Uses passwords, MFA, biometrics, certificates.
Authorization: Determines what a user can do. Uses RBAC, ACLs, permissions.
Accounting: Tracks activity. Uses logs, audit trails, session records.

## AAA Protocols
RADIUS: Centralized AAA for networks. Uses UDP. Used for WiFi, VPN, 802.1X.
TACACS+: AAA for network devices. Uses TCP. Separates authentication and authorization.

## Authentication Protocols (Not AAA)
CHAP: Challenge Handshake Authentication Protocol.
MS-CHAP: Microsoft version of CHAP.
PAP: Password Authentication Protocol. Sends credentials in plaintext.

## Authentication Methods
Password: Something you know.
MFA: More than one factor. Stronger authentication.
Biometrics: Something you are.
Certificates: Cryptographic identity for devices or users.
Not authentication: IP address, MAC address, location.

## Access Control Models
RBAC: Role based access control.
DAC: Owner decides permissions.
MAC: Labels like Confidential and Top Secret.
ABAC: Attribute based access control.

## Security Control Categories
Preventive: Stops attacks. Firewalls, MFA, segmentation, IPS, locks.
Detective: Notices attacks. IDS, logs, cameras, audits.
Corrective: Fixes after attack. Backups, restoration, patching.
Compensating: Alternative control when ideal control is not possible.
Directive: Rules and guidelines. Policies, standards, AUP.

## Security Control Types
Administrative or Managerial: Policies and plans. AUP, training, hiring, IRP, DRP.
Technical or Logical: Technology based security. Firewalls, encryption, ACLs, IDS, MFA tech.
Physical: Tangible barriers. Locks, guards, lighting, fencing.
Operational: Human actions. Log review, patching, backup rotation, incident response.

## Key Terms
AUP: Acceptable Use Policy.
IRP: Incident Response Plan.
DRP: Disaster Recovery Plan.
Non Repudiation: Proving actions cannot be denied. Uses digital signatures and certificates.

