This is when someone injects malicious scripts into a web page so that the code runs in the victim’s browser. That can steal cookies, mess with the DOM, or hijack sessions.  

**Fix:** sanitize and encode all user input/output, use Content Security Policy (CSP), and set cookies with `HttpOnly` and `Secure`.  

**Catch:** monitor IDS/WAF logs for `<script>` tags or unusual parameters in requests, and look for odd browser errors or referrers.