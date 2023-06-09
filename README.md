# Welcome to the Sample Website for Penetration Testing Research!

This repository contains a sample website for penetration testing research, with the goal of finding and documenting security vulnerabilities, and demonstrating proper fixes for them.

## Purpose

The purpose of this sample website is to provide a platform for individuals and organizations to learn about penetration testing and how to properly secure a website from potential security threats. By examining this sample website, individuals will gain hands-on experience in finding and fixing common security vulnerabilities in a web application.

## Key Features

A sample website built with Flask, a popular Python web framework.
Includes common security vulnerabilities found in web applications, such as SQL injection and cross-site scripting (XSS).
Provides step-by-step explanations and demonstrations of proper fixes for the security vulnerabilities found.
Includes a complete documentation of the security vulnerabilities found and the fixes applied.
How to Contribute

We welcome contributions and suggestions to improve this sample website and its documentation. If you have found a security vulnerability or have a suggestion for improvement, please open an issue or submit a pull request.

# Getting Started

## Dependencies and Libraries

This project uses the following dependencies and libraries:

Flask: a lightweight web framework for Python.  
SQLite3: a relational database management system.  
re: a regular expression library for Python.  
bcrypt: a library for password hashing and salting.  
requests: a library for making HTTP requests in Python.  
hashlib: a library for secure hashing of data.  


## Installation

To install the project, follow these steps:

Clone the repository to your local machine.

Install Python 3 if it is not already installed on your machine.
Install the required dependencies by running the following command in your terminal or command prompt:
```
pip install flask bcrypt requests

```
Run the Flask application using the following command:
```
python app.py
```

You should now be able to access the application in your browser at http://localhost:5000/.

## Database Operations

The database used in this project is SQLite. There are several database operations defined in the code that are used to interact with the database:

```
create_database()
```
- This function creates a database connection and creates a table named 'users' if it doesn't already exist. The table has three columns: 'id', 'username', and 'password'.

```
add_user(username, password)
```
- This function adds a new user to the database with the provided username and password. It establishes a connection to the database, inserts a new record into the 'users' table with the provided username and password, and then closes the connection.


```
get_user(username, password)
```
- This function retrieves a user from the database with the provided username and password. It establishes a connection to the database, retrieves the record from the 'users' table with the matching username and password, and then closes the connection.


These database operations are used in the signup and login functions to add new users and retrieve existing users from the database.

## Current security vulnerabilities

✅ -> Implemented  
🚫 -> In progress

### Password storage
✅ The password is stored in the database in plain text, which is a security vulnerability. In case the database gets compromised, the attacker will have access to all the passwords. You should store the passwords securely, for example, using a hash function and a salt.

### Brute-force protection / IP rate-limiting 
✅ The current implementation provides a 5-second countdown timer in case of a failed login attempt, but this is not enough to protect against brute-force attacks. A better solution would be to implement rate limiting or IP blocking after several consecutive failed attempts.

### Input validation
✅ The password checker only checks the length of the password and if it contains both uppercase and lowercase letters. It does not check for other requirements such as the presence of numbers or special characters, which are commonly required for strong passwords.

### Cross-Site Scripting (XSS)
✅ The application does not sanitize user input, which leaves it vulnerable to XSS attacks. An attacker could inject malicious JavaScript into the application, which would execute in the user's browser. To prevent XSS, you should sanitize user input by escaping special characters or using a library that automatically escapes user input.

### Cross-Site Request Forgery (CSRF)
🚫 The application is vulnerable to CSRF attacks. An attacker could trick a user into submitting a malicious request, such as a request to change the password. To prevent CSRF, you should include a unique token in each form and validate it on the server.

### SQL Injection
✅ The application is vulnerable to SQL injection attacks. An attacker could inject malicious SQL statements into the application, which would execute in the database. To prevent SQL injection, you should use parameterized queries or a library that automatically escapes user input.

## Conclusion

We hope that this sample website for penetration testing research will be a valuable resource for individuals and organizations looking to learn about website security and penetration testing. By examining and fixing the security vulnerabilities in this sample website, individuals will gain hands-on experience in securing their own websites from potential security threats.


## Issue solutions

In order to resolve the error:
```
"ImportError: cannot import name 'soft_unicode' from 'markupsafe'"
```

It has been found that the latest version of markupsafe is not compatible with this web app.

As a solution, it is recommended to use version 0.23 of markupsafe in your Flask project. This version has been tested and confirmed to work with the current codebase.

Please update your markupsafe package to the specified version in order to avoid any further compatibility issues.
