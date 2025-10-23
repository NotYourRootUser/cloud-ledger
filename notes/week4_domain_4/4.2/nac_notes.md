# Network Access Control (NAC) Notes

## Anchor
NAC checks devices before granting network access, verifying identity and health (patch level, antivirus, etc.). 
Protocols like 802.1X or tools such as Cisco ISE and Aruba ClearPass perform these checks. 
This prevents unmanaged devices from entering sensitive networks. 
Cloud parallels exist in AWS IAM conditional access or device context verification in Azure AD.

## Reverse
NAC can block legitimate devices in BYOD setups or misjudge posture checks. 
Overly strict policies can interrupt business operations. 
Balance is key—NAC should guide access dynamically instead of being purely binary.
