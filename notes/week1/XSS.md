# Cross-Site Scripting (XSS) Notes (Security+)

- **What it is:** Attacker injects scripts into web pages → runs in victim’s browser. Used to steal cookies/sessions or manipulate pages.

## Types
- Reflected → payload in URL, runs once.
- Stored → payload saved server-side, hits everyone.
- DOM-based → executed via client-side code.

## Detection
- Suspicious `<script>` or `onerror` tags.
- IDS/WAF alerts with script payloads.
- User reports of pop-ups, redirects.
- Scanners (Burp, ZAP).

## CIA Impact
- **Confidentiality:** High (steal tokens/cookies).
- **Integrity:** Medium (modify DOM/data).
- **Availability:** Low.

## Mitigation
- Encode output properly.
- Validate/sanitize input.
- CSP (Content Security Policy).
- Secure/HTTPOnly cookies.

## Tool
- Burp Suite / OWASP ZAP.

## Analogy
- Like graffiti on a shared wall → everyone who passes by sees (and gets affected).
