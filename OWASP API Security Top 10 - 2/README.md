# [Task 4] Vulnerability VIII - Injection
## How does it happen?
- Injection attacks are probably among the oldest API/web-based attacks and are still being carried out by hackers on real-world applications. Injection flaws occur when user input is **not filtered and is directly processed by an API**; thus enabling the attacker to perform unintended API actions without authorisation. 
- An injection may come from Structure Query Language (SQL), operating system (OS) commands, Extensible Markup Language (XML) etc. Nowadays, frameworks offer functionality to protect against this attack through automatic sanitisation of data; however, applications built in custom frameworks like core PHP are still susceptible to such attacks. 

## Likely Impact 
Injection flaws may lead to **information disclosure, data loss, DoS, and complete account takeover**. The successful injection attacks may also cause the intruders to access the sensitive data or even create new functionality and perform remote code execution. 

## Practical Example
- Continue to use the Chrome browser and Talend API Tester for debugging in the VM.
- A few users of company MHT reported that their account password had changed, and they could not further log in to their original account. Consequently, the dev team found that Bob had developed a vulnerable login API endpoint `/apirule8/user/login_v` that is not filtering user input.
- A malicious attacker requires the username of the target, and for the password, they can use the payload `' OR 1=1--'` and get an authorisation key for any account (as shown below).

## Mitigation Measures
- Ensure to use a well-known library for client-side input validation.
- If a framework is not used, all client-provided data must be validated first and then filtered and sanitised. 
Add necessary security rules to the Web Application Firewall (WAF). Most of the time, injection flaws can be mitigated at the network level.
- Make use of built-in filters in frameworks like Laravel, Code Ignitor etc., to validate and filter data. 

## Q1. Can injection attacks be carried out to extract data from the database (yea/nay)?
yea
## Q2. Can injection attacks result in remote code execution (yea/nay)?
yea
## Q3. What is the HTTP response code if a user enters an invalid username or password?
403

# 





---

# Reference
- [](https://tryhackme.com/r/room/owaspapisecuritytop10d0)