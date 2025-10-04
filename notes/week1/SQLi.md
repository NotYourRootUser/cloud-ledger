# SQL Injection (SQLi) Notes (Security+)

- **What it is:** Attacker injects SQL into app input, database executes it. Can expose, alter, or delete data.

## Detection
- App shows DB errors/stack traces.
- Query returns too many rows.
- WAF/IDS alerts (payloads like `' OR '1'='1`).
- DB logs show odd queries.

## Containment
- Temporarily disable vulnerable form or app page.
- Patch and sanitize input validation code immediately.
- Review DB logs for suspicious queries executed.
- Rotate credentials and re-issue compromised DB accounts.

## CIA Impact
- **Confidentiality:** High
- **Integrity:** High
- **Availability:** Medium

## Common Causes
- Concatenating user input into SQL.
- No input validation/escaping.
- Over-privileged DB accounts.

## Mitigation
- Parameterized queries / prepared statements.
- Input validation (whitelists).
- Least privilege DB permissions.
- WAF signatures.
- Monitor query logs.
- Stored procedures (with parameterized queries).
- Disable detailed error messages (generic error handling).

## Tool
- sqlmap (scanner/exploit).

## Analogy
- Like slipping extra instructions on a restaurant order — chef executes blindly unless menu IDs are enforced.
