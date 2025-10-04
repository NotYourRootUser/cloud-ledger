# Week 1 — DVWA Lab (SQLi & Reflected XSS)

**Quick note**  
Ran a local DVWA lab to confirm two common web vulnerabilities: **SQL Injection (SQLi)** and **Reflected XSS**. Steps, screenshots and brief notes are included in the repo.

## Quick setup
1. Start DVWA (Docker or XAMPP).  
2. Open `http://localhost:8080/` and log in with `admin` / `password`.  
3. Click **Setup / Reset DB** and set **DVWA Security = Low**.

## What I demonstrated
- **SQLi:** Injected a payload that returned user rows from the database (app passed untrusted input to the DB).  
  ![SQLi screenshot](sqli-screenshot.png)

- **Reflected XSS:** Submitted a small script that was reflected back and executed in the page (output not escaped).  
  ![XSS screenshot](xss-screenshot.png)

## Files / artifacts
- [DVWA-checklist.md](DVWA-checklist.md) — setup checklist and verification steps.  
- [sqli-steps.md](sqli-steps.md) — payloads and commands used for SQLi.  
- [xss-steps.md](xss-steps.md) — exact steps for triggering the XSS.  
- [compression.md](compression.md) — short summary, suggested fixes, and test notes.

## Short takeaway / next step
Both issues were reproducible on **Low** security. Next action: implement fixes (use parameterized queries and output encoding) and re-test to confirm the vulnerabilities are closed.
