# DVWA Penetration Testing Report

This project contains a set of vulnerability exploitation reports based on the [Damn Vulnerable Web Application (DVWA)](https://owasp.org/www-project-damn-vulnerable-web-sockets/). The goal of this project is to demonstrate practical knowledge in identifying, exploiting, and documenting common web vulnerabilities as part of my learning path toward a career in cybersecurity and penetration testing.

---
## 🛠 Tools & Utilities Used

- **DVWA (Damn Vulnerable Web Application)**  
  Used as the vulnerable web application target for practicing and demonstrating common web application security vulnerabilities.

- **Burp Suite Community Edition**  
  Used for intercepting, analyzing, and modifying HTTP requests/responses during testing, especially useful in XSS and command injection exploitation.

- **OWASP ZAP**  
  Used for passive scanning and identifying security misconfigurations in the DVWA target.

- **curl**  
  Utilized for crafting raw HTTP requests in command injection and SSRF testing scenarios.

- **Nikto**  
  Performed basic vulnerability scanning of the DVWA instance to enumerate server-level misconfigurations.

- **Nmap**  
  Used to discover open ports and running services on the DVWA host as part of a pre-engagement scan.

- **Git**  
  Version control used to manage and track changes in the documentation and code artifacts.

- **Obsidian**  
  Used to organize structured reports in Markdown, enabling easy linking and internal navigation between vulnerabilities.

---
## 📌 Covered Vulnerabilities

Each report includes technical description, exploitation steps, screenshots, payloads used, and proposed mitigations.

- [Command Injection](report/command-injection.md)
- [SQL Injection](report/sql-injection.md)
- [Reflected XSS](report/reflected-xss.md)
---
## 🎯 Key Objectives

- ✅ Understand the practical execution of common OWASP Top 10 vulnerabilities
- ✅ Practice safe and ethical exploitation in a controlled environment
- ✅ Build a technical portfolio for cybersecurity job applications

---
## 🚨 Disclaimer

> This project was conducted in a **fully legal**, **isolated**, and **self-contained environment** for educational purposes only.  
> I do **not** condone or support illegal hacking or unauthorized penetration testing.

---
## 📚 References

- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings)
- [PortSwigger Web Security Academy](https://portswigger.net/web-security)

---
## 🙋‍♂️ About Me

I'm transitioning into cybersecurity from a QA background. This repository is a part of my continuous learning and effort to demonstrate practical skills and build credibility as a future penetration tester or security specialist.
 
