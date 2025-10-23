# Secure DNS Notes

DNSSEC adds digital signatures to DNS records so attackers cannot forge them. It keeps name resolution trustworthy but not private.
Sinkholing redirects traffic away from known bad domains to a safe address so infected systems cannot contact attackers.
Reputation services use intelligence lists to block requests to known malicious sites.

Commands to test DNSSEC:
dig +dnssec example.com
dig dnskey example.com

To test sinkholing, you can edit the hosts file to redirect a fake domain to 127.0.0.1.

DNSSEC protects integrity. Sinkholes and reputation systems add control and containment.
