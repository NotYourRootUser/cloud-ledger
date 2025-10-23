# Secure DNS Notes

## Anchor
Secure DNS practices protect name resolution from spoofing and abuse. DNSSEC adds digital signatures to DNS records so resolvers can verify authenticity of responses. Sinkholing redirects known malicious domain names to a controlled address to prevent infected hosts from contacting attacker infrastructure. Reputation services and threat intelligence feeds provide lists of malicious domains and IPs that can be blocked at DNS or proxy layers.

Real world examples include enabling DNSSEC for a public zone and validating it on authoritative and recursive resolvers. Cloud providers offer managed DNS with DNSSEC support. Organizations often use a recursive resolver that applies threat intelligence to return NXDOMAIN for known malicious domains or route them to a sinkhole IP for monitoring. Testing DNSSEC can be performed with the dig tool and the +dnssec flag, for example dig +dnssec example.com.

## Reverse
DNSSEC provides integrity but not confidentiality. If DNSSEC is misconfigured it can break resolution for legitimate users, so careful testing and staged rollouts are required. Relying solely on reputation lists can block newly created malicious domains that are not yet listed, and false positives may affect business systems that rely on third party services. Sinkholes must be monitored; silently dropping traffic without visibility can hinder incident response. Combine DNSSEC, monitoring, and reputation-based filtering for layered protection.
