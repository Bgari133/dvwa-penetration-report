
---
# Reflected Cross-Site Scripting (XSS)

## ✅ Security Level
DVWA Security Level: **Low**

## 🔍 Vulnerable Field
The message input field in the **XSS (Reflected)** module.

## 💥 Payload Used
```html
<script>alert('XSS')</script>
```
## 📸 Result

A JavaScript alert box appeared, proving that the script was executed.

(See screenshot: [xss.png](../screenshots/xss.png))

## 🧠 Explanation

The application does not sanitize user input before displaying it in the browser:

```html
<p>You entered: <script>alert('XSS')</script></p>
```
As a result, attackers can inject malicious JavaScript that can steal cookies, redirect users, or manipulate the page.

## 🛡️ Mitigation

- **Input Sanitization**: Encode special characters to prevent script execution.
    
- **Content Security Policy (CSP)**: Restrict inline JavaScript execution.
    
- **Use HTTPOnly Cookies**: Prevent cookie theft via JavaScript.