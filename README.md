# FUTURE_CS-01
web Application vulnerabilities Testing
Project: Web Application Security Testing (OWASP Juice Shop)
Submitted By: SK. Lathi Funnisa Begam
Role: Cyber Security Intern
Tools Used: OWASP ZAP, Burp Suite, Browser DevTools

📌 1. **Objective of the Task**

✅ Set up a vulnerable web application (OWASP Juice Shop/DVWA)
✅ Identify vulnerabilities using tools (OWASP ZAP, Burp Suite, Nikto)
✅ Perform manual testing (SQLi, XSS, CSRF, IDOR)
✅ Map vulnerabilities to OWASP Top 10 (2021)
✅ Document screenshots, impact level, and mitigation steps
✅ Submit a professional-style Security Report (PDF/GitHub)

🛠 2. **Tools & Technologies Used**
Tool	Purpose
OWASP Juice Shop	Test Web Application
OWASP ZAP	Automated scanning
Burp Suite	Manual penetration testing
Nikto	Web server vulnerability scanning
Docker / LocalHost	Application hosting
Browser DevTools	Debugging / Inspecting requests

🔍 3. **Testing Methodology**
Information Gathering
Enumerated pages, API endpoints, and user roles
Automated Scanning – OWASP ZAP & Nikto reports generated
Manual Testing
SQL Injection, XSS, IDOR, CSRF validated
Exploitation & Screenshot Collection
Documentation & OWASP Top 10 Mapping

⚠ 4. **Vulnerabilities Found:**
ID	Vulnerability	Risk	Description
V1	SQL Injection (Login Page)	High	' OR '1'='1 bypasses login authentication
V2	Stored XSS	High	Injected <script>alert('XSS')</script> in feedback section
V3	CSRF (Change Email Request)	High	Exploited without user confirmation
V4	IDOR (Order Details Access)	High	Accessed /api/orders/1 by changing ID
V5	Weak Password Policy	Medium	Accepts passwords like 12345
V6	Missing Security Headers	Low	No CSP / X-Frame-Options in response headers



📉 5. **Impact Summary:**
Vulnerability	Impact
SQL Injection	Full account takeover, database exposure
XSS	Session hijacking, user data theft
IDOR	Unauthorized access to other users’ data
CSRF	User actions executed without consent
Weak Passwords	Brute force risk
No Security Headers	Clickjacking, data exposure

🛡 6. **Mitigation & Recommendations**
Issue	Recommendation
SQL Injection	Use prepared statements, parameterized queries
XSS	Validate & encode input, implement CSP
CSRF	Add anti-CSRF tokens, secure cookies
IDOR	Check user authorization server-side
Weak Passwords	Enforce strong password policy
Missing Headers	Add Content-Security-Policy, X-Frame-Options, HSTS


📊 7. **OWASP Top 10 (2021) Mapping**
OWASP ID	Name	Status in App
A01	Broken Access Control	✅ IDOR
A02	Cryptographic Failures	⚠ Not observed
A03	Injection	✅ SQL Injection
A04	Insecure Design	⚠ General observations
A05	Security Misconfiguration	✅ Missing headers, default configs
A06	Vulnerable & Outdated Components	⚠ Suggested upgrade check
A07	Auth Failures	✅ Weak password policy
A08	Software/Data Integrity Failures	✅ CSRF
A09	Security Logging Failures	⚠ Limited logging
A10	SSRF	❌ Not found


✅ 8. **Conclusion**

The application is intentionally vulnerable for practice but demonstrates real-world security flaws.

Critical vulnerabilities such as SQL Injection, XSS, CSRF, and IDOR were successfully exploited.

With proper security controls and re-testing, these issues can be fully remediated.



📚 10. **References**

https://owasp.org/www-project-juice-shop/

https://owasp.org/Top10/

OWASP ZAP & Burp Suite documentation
