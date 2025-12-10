# Attack Delivery and Social Engineering Notes

## Delivery Channels
**Email:** primary attack surface for phishing and malware delivery.  
**QR Codes:** attackers replace legitimate QR labels to redirect to malicious sites.  
**SMS:** trusted personal channel used for smishing attacks and fake delivery updates.  
**Voice Calls:** phone calls used for authority scams and extracting MFA codes.  
**Removable Media:** USB drives dropped in public to tempt victims into plugging them in.

## Social Engineering Types
**Phishing:** fake email designed to steal credentials or deliver malware.  
**Smishing:** phishing over SMS text messaging with malicious links.  
**Vishing:** voice based manipulation through fake phone calls.  
**Pretexting:** attacker creates a believable story to justify requests.  
**Impersonation:** attacker pretends to be a trusted person.  
**BEC:** attacker hijacks or spoofs business email accounts to request fund transfers.

## Supporting Attack Paths
**Supply Chain Attacks:** compromise through trusted vendors or poisoned software updates.  
**Default Credentials:** factory set passwords like admin admin not changed.  
**Misconfiguration:** insecure settings allow easy compromise such as public S3 buckets or MFA disabled.

## Attack Flow Summary
Delivery → Social engineering tactic → Target action → Amplifiers such as misconfig → Attack outcome

## BEC Attack Flow

yaml
Copy code
        Initial Access
               |
               v
    Attacker compromises mailbox
    (password reuse or phishing)
               |
               v
    Inbox observation phase
  attacker reads conversations
  watches invoice and payment cycles
               |
               v
 Attacker crafts believable message
pretending to be executive or vendor
               |
               v
  Target receives email instruction
usually finance or accounts payable staff
|
v
Social engineering triggers payment action
urgency or authority pressure
|
v
Funds transferred to attacker account
or attacker controlled mule destination
|
v
Attacker clears traces or
maintains mailbox persistence

Copy code
