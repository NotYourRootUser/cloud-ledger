# Network & Web Attack Notes (Humanized)

## MITM (Man-in-the-Middle)
This is when an attacker slips between two people who are communicating. They can just listen quietly (passive) or actually change what’s being said (active).  
Visualize it like:  
`Party ===== Attacker ===== Party`

---

## SQL Injection (SQLi)
Here, the attacker puts malicious SQL into an input field. If the app doesn’t handle it properly, the database runs those commands. That means the attacker can read, change, or delete data.  

**How to stop it:** use parameterized queries or prepared statements so user input is always treated as plain data, not part of the SQL command.  

**How to catch it:** keep an eye on DB query logs and WAF/IDS alerts for weird SQL-looking payloads (like `' OR '1'='1'` or `UNION SELECT`) or strange error patterns.

---

## Cross-Site Scripting (XSS)
This is when someone injects malicious scripts into a web page so that the code runs in the victim’s browser. That can steal cookies, mess with the DOM, or hijack sessions.  

**Fix:** sanitize and encode all user input/output, use Content Security Policy (CSP), and set cookies with `HttpOnly` and `Secure`.  

**Catch:** monitor IDS/WAF logs for `<script>` tags or unusual parameters in requests, and look for odd browser errors or referrers.

---

## DoS / DDoS
A denial-of-service attack just overwhelms a system with traffic.  
- **DoS** comes from one source.  
- **DDoS** comes from many sources at once.  
The result: real users can’t get service.

---

## Vulnerability Scanning
These are automated scans that check systems, apps, or networks for known issues, misconfigs, or missing patches.  

Two types:  
- **Credentialed scan** — uses valid logins, digs deep into configs.  
- **Non-credentialed scan** — no logins, so it only sees the surface (external view).

---

## Buffer Overflow
This happens when a program is sent more data than a memory buffer can hold. The overflow can crash the app or let an attacker run their own code.
