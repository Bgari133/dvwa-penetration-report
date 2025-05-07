# 📄 **DVWA Brute Force Report**

# Brute Force Attack (Low Security Level)

## ✅ Security Level

DVWA Security Level: **Low**

---
## 🔍 Vulnerable Field

The login input fields (**username** and **password**) in the **Brute Force** module.

---
## 💥 Payload Used

Common username and password lists (e.g., admin/password).

- Wordlist source: [SecLists repository](https://github.com/danielmiessler/SecLists)

---
## 📸 Result

Successfully identified valid credentials through brute-forcing.

(See screenshot: brute_force.png)

---
## 🧠 Explanation

The DVWA application does not implement rate limiting, account lockout mechanisms, or CAPTCHA protection at the low security level, allowing unlimited authentication attempts.

---
## ⚠️ Additional Notes

When using `hydra` to automate brute forcing, it is possible that the tool might indicate successful credential discovery, yet the credentials may not actually grant access due to false positives or improper response detection.

---
## 🛡️ Mitigation

- **Account Lockout:** Implement lockouts after a certain number of failed attempts.
    
- **CAPTCHA Protection:** Use CAPTCHAs to differentiate human users from bots.
    
- **Rate Limiting:** Restrict the number of login attempts within a given timeframe.
    
- **Monitoring and Alerting:** Track unusual login patterns and generate alerts on suspected brute-force attempts.