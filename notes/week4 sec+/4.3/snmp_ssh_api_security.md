# SNMP v3 SSH and API Security

## Anchor
Always prefer encrypted management protocols. Replace Telnet and SNMP v1/v2 with SNMP v3 and SSH. For APIs, enforce HTTPS and signed requests.

Example: Use SSH key-based authentication and disable password logins. When using APIs for SDN or IaC, store tokens securely.

## Recall
- Why is SNMP v2 insecure?
- What key feature makes SNMP v3 safer?
- What happens if an API key is stored in plain text in a repo?