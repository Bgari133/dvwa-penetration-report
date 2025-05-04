# Command Injection (Low Security Level)

## ✅ Security Level
DVWA Security Level: **Low**

## 🔍 Vulnerable Field
The IP address input field in the **Command Injection** module.

## 💥 Payload Used
	127.0.0.1 && whoami


## 📸 Result
The web application executed the injected command and returned the output:
(See screenshot: [cmd_injection.png](../screenshots/cmd_injection.png))

## 🧠 Explanation
The input is inserted directly into a system shell command, like:
```bash
ping -c 4 127.0.0.1 && whoami
```

## 🛡️ Mitigation

- **Validate input**: only allow valid IP addresses using strict patterns.
    
- **Sanitize shell input**: use functions like `escapeshellcmd()` or `escapeshellarg()` in PHP.
    
- **Avoid shell calls**: use safer APIs that do not invoke the shell.
