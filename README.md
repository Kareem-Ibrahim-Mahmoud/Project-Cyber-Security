# Security Assessment Report

## 1. Assessment Scope
**Target IP / URL:** 203.0.113.42  
**Tools Used:** Other ✅ (e.g., SQLMAP)

---

## 2. Findings Summary

| Vulnerability Name       | Severity | Status     |
|--------------------------|----------|------------|
| SQL Injection Attempt    | High     | Confirmed  |
| Malicious Automation     | High     | Confirmed  |
| URL Encoding Injection (%27) | Medium | Confirmed  |

---

## 3. Technical Evidence
*Paste screenshot verification below:*  
<img width="1920" height="1080" alt="Screenshot (2116)" src="https://github.com/user-attachments/assets/0431d55c-fb25-4705-a035-81f2021df684" />
<img width="1920" height="1080" alt="Screenshot (2117)" src="https://github.com/user-attachments/assets/7bc6257d-f363-4608-8189-a5868fb0b651" />



---

## 4. Recommendations

1. **Implement Input Validation & Sanitization**  
   Apply strict filtering to user input on the search page to prevent the entry of symbols such as `'`, `UNION`, and `SELECT`.

2. **Use Prepared Statements / Parameterized Queries**  
   Modify the code to use secure queries that prevent the execution of user-generated SQL commands.

3. **Enable Web Application Firewall (WAF)**  
   Enable WAF, such as ModSecurity, to automatically prevent SQL Injection attacks and block suspicious bots.

4. **Block Attacker IP (203.0.113.42)**  
   Add the attacker's IP to the server-level or firewall block list to prevent re-attacks.

5. **Implement Rate Limiting on Search Endpoint**  
   Limit the number of requests allowed per IP per minute to prevent automated attacks (bots/SQLMAPs).

6. **Disable Detailed Error Messages**  
   Disable detailed error messages that could help an attacker understand the database structure.

7. **Regular Log Monitoring**  
   Monitor server logs daily for early detection of abnormal activity.

