
Fundamentals of MySQL

Most modern web applications rely on a database structure on the back-end. These databases store and retrieve data related to the application, ranging from web content to user information. To make an application dynamic, it must interact with the database in real-time. As HTTPS requests are received from users, the back-end issues queries to the database to build appropriate responses. These queries often include data from the HTTPS request or other relevant information.
<img width="1132" height="398" alt="Image" src="https://github.com/user-attachments/assets/101474b2-7fe7-4045-8e70-ae4c5ecfa999" />

When user-supplied input is used to construct database queries, malicious users may manipulate this input to alter the query’s behavior, granting themselves unintended access to the database. This type of attack is known as SQL Injection (SQLi).

SQL Injection targets relational databases like MySQL, while attacks against non-relational databases (such as MongoDB) are referred to as NoSQL Injection. This document focuses on MySQL as an introduction to SQL Injection concepts.
SQL Injection

There are various types of injection vulnerabilities in web applications, including HTTP header injection, code injection, and command injection. However, SQL Injection remains one of the most common and dangerous.
A SQL Injection occurs when a malicious user submits crafted input that alters the final SQL query sent by the application to the database, allowing the user to execute unintended queries directly.

To successfully exploit this vulnerability, an attacker must inject SQL code and manipulate the web application's logic — either by altering the intended query or by introducing an entirely new query. Typically, this is done by injecting characters like single quotes (') or double quotes (") to break out of the intended input context and inject malicious SQL code.
Use Cases and Impact

SQL Injection vulnerabilities can have a severe impact, especially if the back-end database permissions are overly permissive.

Attackers can:

    Exfiltrate sensitive data such as usernames, passwords, or credit card numbers, which can later be abused for further malicious purposes.

    Breach accounts, perform identity theft, or abuse leaked data in other services.

    Bypass authentication mechanisms (e.g., log in without valid credentials).

    Access restricted areas (e.g., admin panels).

    Read and write arbitrary files on the back-end server, potentially implanting backdoors and taking over the entire system.

SQL Injection has been responsible for countless data breaches globally and remains a prevalent threat today.
Prevention

SQL Injections typically result from poorly written code or improperly configured database permissions.
To mitigate these risks, developers should follow secure coding practices, such as:

    Properly sanitizing and validating all user inputs.

    Using parameterized queries (prepared statements).

    Restricting database privileges following the principle of least privilege.

Introduction to Databases

Before diving deeper into SQL Injection, it's important to understand the basics of databases and Structured Query Language (SQL).
Databases store various types of data used by web applications — from assets like images and files to dynamic content like posts, and sensitive information like user credentials.

Historically, applications used file-based storage, which became impractical as data volumes grew. This limitation led to the adoption of Database Management Systems (DBMS).
Database Management Systems (DBMS)

A DBMS provides tools to create, define, host, and manage databases. Over time, several types of DBMS have been developed, including:

    File-based

    Relational (RDBMS)

    NoSQL

    Graph-based

    Key/Value stores

Interaction with a DBMS can be done via command-line tools, graphical interfaces, or APIs. DBMS solutions are widely used across industries like banking, finance, and education for storing and managing large datasets.

Key DBMS features include:

    Concurrency: Supports multiple simultaneous users without corrupting data.

    Consistency: Ensures data remains accurate despite concurrent access.

    Security: Enforces access controls through authentication and permissions.

    Reliability: Provides backup and restore mechanisms for recovery.

    SQL: Simplifies interactions with databases via a standardized, intuitive query language.

Architecture

The diagram below illustrates a two-tier architecture:
<img width="1388" height="398" alt="Image" src="https://github.com/user-attachments/assets/fb3b5b74-7a79-4442-a03b-096ef3e85d0c" />

Tier I typically consists of client-side applications (websites, GUI programs) handling user interactions like logging in or posting comments. These actions communicate with Tier II via API calls or requests.

Tier II serves as middleware, translating requests into database operations via DBMS-specific drivers or libraries. The DBMS then executes operations such as insertion, retrieval, updates, or deletions, and returns the results.

For scalability and performance, large databases often run on separate dedicated servers rather than sharing resources with the application server.
Types of Databases

Databases are generally categorized into:

    Relational Databases (SQL-based)

    Non-Relational Databases (NoSQL)

Relational databases use SQL for structured interactions, while non-relational databases employ various other models and query methods.
