# Web Application Security Testing

## 1. Project Overview

This project demonstrates practical security testing of common web application vulnerabilities using the Damn Vulnerable Web Application (DVWA) in a controlled local laboratory environment.

The assessment focuses on three major vulnerabilities:

- SQL Injection (SQLi)
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)

The repository contains attack scenarios, observed results, security impacts, and mitigation techniques for each vulnerability.

## 2. Testing Environment

The testing was performed in a controlled local environment using:

- Operating System: Kali Linux
- Web Application: DVWA
- Web Server: Apache
- Database: MariaDB
- Security Testing Tool: Burp Suite
- Browser: Burp Suite Embedded Browser

## 3. Vulnerabilities Tested

### SQL Injection

SQL Injection was tested by providing crafted input to the DVWA SQL Injection module.

**Mitigation:** Prepared statements and parameterized queries.

### Cross-Site Scripting

Reflected and Stored XSS were tested using JavaScript payloads.

**Mitigation:** Output encoding, input validation, and Content Security Policy.

### Cross-Site Request Forgery

CSRF was tested against the DVWA password-change functionality using Burp Suite.

**Mitigation:** Anti-CSRF tokens and appropriate request validation.

## 4. Tools Used

- Kali Linux
- DVWA
- Apache
- MariaDB
- Burp Suite
- Web Browser

## 5. Project Objective

The objective of this project is to understand common web application vulnerabilities, demonstrate their behavior in a controlled environment, and document appropriate security controls for mitigating them.

## 6. Disclaimer

All security testing documented in this repository was performed against a controlled DVWA laboratory environment for educational purposes.