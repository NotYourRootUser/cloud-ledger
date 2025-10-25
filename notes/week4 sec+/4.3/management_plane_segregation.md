# Management Plane Segregation

## Anchor
Keep the management plane separate from user or data traffic. Use dedicated VLANs, subnets, or even physical networks (OOB - Out of Band). Limit access to admins and monitoring systems only.

Example: Use a management VLAN that only allows SSH or HTTPS from trusted IPs. Combine with jump hosts or VPNs.

## Recall
- What is the purpose of separating management traffic?
- How could a single flat network create security risks?
- Which AWS component acts like an OOB network for management access?