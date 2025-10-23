# Mail Security Notes

## Anchor
Mail security ensures messages come from who they claim to. 
SPF validates the sender’s IP, DKIM signs the message with a private key, and DMARC sets the policy for handling failures. 
Together, they block email spoofing and phishing. Gmail, Microsoft 365, and AWS SES rely on these standards to protect domains. 
For example, DMARC 'reject' policies drop spoofed emails outright.

## Reverse
Misconfigured SPF or DKIM can cause legitimate emails to be rejected. 
Short DKIM keys or lack of rotation can be exploited. 
Domains with 'none' DMARC policies only get reports but no protection. 
Always validate new mail settings before enforcing strict rejection.
