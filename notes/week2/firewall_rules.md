**Firewall ACL Rules**

- Allow HTTPS (443) inbound to web server only
ACL that permits TCP 443 to 10.0.1.10 from anywhere, denies everything else.

- Allow SSH only from admin subnet
ACL that permits TCP 22 to 10.0.1.10, but only from 192.168.50.0/24.

- Deny all ICMP (ping) traffic
ACL that drops ICMP packets globally.