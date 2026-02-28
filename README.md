# SQL Injection on DVWA
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

## How It Works
Backend query (Low security mode):
```sql
SELECT * FROM users WHERE user_id = '$id';

**Target:** DVWA → SQL Injection page  
**Payload Used:**
SELECT * FROM users WHERE user_id = '1' OR '1'='1';

## Result
Successfully retrieved all user records.
Confirmed SQL Injection vulnerability.
Demonstrated lack of input validation.

##Conclusion
This project demonstrates how improper input handling can lead to SQL Injection. Secure coding practices such as prepared statements and input validation are necessary to prevent such attacks.

##Author
Krisha Shah
