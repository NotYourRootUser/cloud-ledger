# SQL Injection (SQLi) Notes (Security+)

- **What it is:** Attacker injects SQL into app input, database executes it. Can expose, alter, or delete data.

## Detection
- App shows DB errors/stack traces.
- Query returns too many rows.
- WAF/IDS alerts (payloads like `' OR '1'='1`).
- DB logs show odd queries.

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

## Tool
- sqlmap (scanner/exploit).

## Analogy
- Like slipping extra instructions on a restaurant order — chef executes blindly unless menu IDs are enforced.
