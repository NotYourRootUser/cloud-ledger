# Week 1 — DVWA Lab (SQLi + XSS)

**What I did (quick):**  
I ran a simple DVWA lab to prove two common web bugs: SQL Injection (SQLi) and Reflected XSS.  
This is a learning exercise — steps, screenshots and short notes are in the repo.

## Quick setup
1. Start DVWA (Docker or XAMPP).  
2. Go to `http://localhost:8080/` and log in (`admin` / `password`).  
3. Click **Setup / Reset DB** and set **DVWA Security = Low**.

## What I proved
- **SQLi:** Used a payload that returned user rows from the database.  
  ![SQLi screenshot](sqli-screenshot.png)

- **XSS (Reflected):** Submitted a small script that got reflected back in the page.  
  ![XSS screenshot](xss-screenshot.png)

## Files / artifacts
- [DVWA-checklist.md](DVWA-checklist.md) — lab checklist.  
- [sqli-steps.md](sqli-steps.md) — short notes of SQLi steps.  
- [xss-steps.md](xss-steps.md) — short notes of XSS steps.  
- [compression.md](compression.md) — summary + mitigation notes.  

## Short takeaway / next step
I proved the bugs work on **Low** security.  
Next: add simple fixes (parameterized queries + output encoding) and re-test.
