Here, the attacker puts malicious SQL into an input field. If the app doesn’t handle it properly, the database runs those commands. That means the attacker can read, change, or delete data.  

**How to stop it:** use parameterized queries or prepared statements so user input is always treated as plain data, not part of the SQL command.  

**How to catch it:** keep an eye on DB query logs and WAF/IDS alerts for weird SQL-looking payloads (like `' OR '1'='1'` or `UNION SELECT`) or strange error patterns.