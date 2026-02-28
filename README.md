# SQL Injection on DVWA (Low Security)

## Objective
To demonstrate a SQL Injection vulnerability using DVWA (Damn Vulnerable Web Application) with security level set to LOW.

## Environment
- Kali Linux
- Apache2
- MariaDB
- PHP
- DVWA

## Setup Steps
1. Installed Apache, MariaDB, and PHP.
2. Cloned DVWA into `/var/www/html/`.
3. Created database `dvwa` and configured `config.inc.php`.
4. Restarted Apache.
5. Opened: http://localhost/DVWA
6. Logged in (admin / password).
7. Set DVWA Security level to **Low**.

## SQL Injection Performed
1' OR '1'='1

## Result
The injection successfully bypassed input validation and displayed all user records from the database, confirming the presence of a SQL Injection vulnerability.

## Conclusion
This project demonstrates how improper input validation can allow attackers to manipulate SQL queries and access sensitive data. It highlights the importance of secure coding practices such as using prepared statements, parameterized queries, and proper input sanitization to prevent SQL Injection attacks.

## Author
Krisha Shah  

## How It Works
Backend query (Low security mode):
```sql
SELECT * FROM users WHERE user_id = '$id';

**Target:** DVWA → SQL Injection page  
**Payload Used:**
SELECT * FROM users WHERE user_id = '1' OR '1'='1';
