# 📄 **DVWA Cross-Site Request Forgery (CSRF) Report**

# CSRF Attack (Low Security Level)

## ✅ Security Level

DVWA Security Level: **Low**

---
## 🔍 Vulnerable Functionality

The **Change Password** form in the **CSRF** module is vulnerable. It allows password changes without proper validation of the user's intention.

---
## 💥 Exploit Example

An attacker crafts a malicious HTML form that submits a POST request to change the victim's password when the victim visits a malicious website.
```
<form action="http://localhost/DVWA/vulnerabilities/csrf/" method="POST">
  <input type="hidden" name="password_new" value="attackerpass" />
  <input type="hidden" name="password_conf" value="attackerpass" />
  <input type="submit" value="Submit" />
</form>
<script>
  document.forms[0].submit();
</script>
```

---
## 📸 Result

The victim's password is silently changed to `attackerpass` without their knowledge when they visit the attacker's page.

(See screenshot: csrf_exploit.png)

---
## 🧠 How the Vulnerability Works

- **Lack of Anti-CSRF Tokens:** The vulnerable form does not include any CSRF token that ties the request to the user's session.
- **Session Cookies:** Browsers automatically include session cookies with cross-origin requests, allowing the forged request to be authenticated as if made by the victim.
- **No Origin/Referer Check:** The server does not check the `Origin` or `Referer` headers to validate the request source.

This allows an attacker to trick authenticated users into submitting unintended requests to the application.

---
## 🔧 Using Burp Suite

Burp Suite can be used to:

1. **Intercept the Legitimate Request:**
    
    - Log in as a valid user and submit a password change request.
        
    - Capture the request in Burp Proxy to study its structure.
        
2. **Send to Repeater:**
    
    - Modify and replay the captured request multiple times to confirm that no CSRF protection is enforced.
        
3. **Generate CSRF PoC:**
    
    - Use Burp’s **CSRF PoC Generator** (right-click the request → "Engagement tools" → "Generate CSRF PoC") to quickly build the malicious form for exploitation.

---
## 🛡️ Mitigation

- **Anti-CSRF Tokens:** Implement unpredictable tokens tied to the user session and verify them server-side.
- **SameSite Cookies:** Set cookies with `SameSite=Strict` or `SameSite=Lax` to prevent them from being sent in cross-site requests.
- **Origin/Referer Validation:** Validate the source of sensitive requests using the `Origin` or `Referer` header.

---
## References

- [OWASP CSRF Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)
- [OWASP Testing Guide: CSRF Testing](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/06-Session_Management_Testing/05-Testing_for_Cross_Site_Request_Forgery)
- [MDN Web Docs: SameSite cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite)
