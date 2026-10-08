# DVWA SQL Injection Lab

## Objective

Identify and validate SQL Injection in the intentionally vulnerable DVWA application.

## Lab Environment

- Kali Linux
- DVWA
- Docker
- Burp Suite
- SQLmap
- Firefox

## Tools Used

- Burp Suite
- SQLmap
- Firefox

## Methodology

1. Accessed the DVWA SQL Injection functionality.
2. Intercepted and inspected HTTP requests using Burp Suite.
3. Tested the `id` parameter with controlled SQL injection payloads.
4. Observed the application's response.
5. Used SQLmap to validate the injection in the authorized lab environment.

## Vulnerability

**SQL Injection (SQLi)**

The `id` parameter was vulnerable to SQL injection because user-controlled input was incorporated into the database query without adequate protection.

## Evidence

A controlled SQL injection payload caused the application to return multiple user records instead of the expected single record.

## Impact

An attacker could potentially manipulate database queries and access unauthorized database information.

## Severity

**Critical**

Estimated CVSS v3.1: **9.8**

## Remediation

- Use prepared statements/parameterized queries.
- Validate user input.
- Apply least-privilege database permissions.
- Avoid displaying detailed database errors.
- Perform regular security testing.

## Screenshots

Screenshots demonstrating the testing process are available in the `screenshots` folder.

## Ethical Use

This testing was performed only against an intentionally vulnerable DVWA instance in an isolated laboratory environment for educational and defensive security purposes.
