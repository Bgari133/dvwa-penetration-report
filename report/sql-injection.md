
---

# 📄 **SQL Injection Report**

# SQL Injection (Low Security Level)

## ✅ Security Level
DVWA Security Level: **Low**

## 🔍 Vulnerable Field
The user ID input field in the **SQL Injection** module.

## 💥 Payload Used
	1' OR '1'='1


## 📸 Result
The application returned a full list of users from the database.

(See screenshot: [sql_injection.png](../screenshots/sql_injection.png))

## 🧠 Explanation
The input is directly inserted into the SQL query:
```sql
SELECT * FROM users WHERE id = '1' OR '1'='1';
```

## 🛡️ Mitigation

- **Use Prepared Statements**: Avoid raw SQL queries and use parameterized queries.
    
- **Filter Input**: Only allow numeric values for the user ID.
    
- **Least Privilege**: Use a low-privilege database user to prevent full table access.