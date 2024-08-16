# Setup
- Set Burp and foxyproxy, instructions can be found in this tutorial on Medium [Burp Suite and Foxy Proxy Setup](https://medium.com/@DatBoyBlu3/burp-suite-and-foxy-proxy-setup-67d5c1d86f8c).

# [Task 3] Inject the juice

## Q1. Log into the administrator account!
To log in the account, make sure the `Intercept is on`. <br>
![](./screenshots/01.png) <br>

After randomly log in with random email and password, Burp receives them all. <br>
![](./screenshots/02.png) <br>

Modify the emali to `' or 1=1 -- `, then press `forward`. <br>
Then turn off that `Intercept is off.`
![](./screenshots/03.png) <br>

Now we log in as the admin.
![](./screenshots/04.png) <br>

The flag is showing up. <br>
![](./screenshots/05.png) <br>

```
32a5e0f21372bcc1000a6088b93b458e41f0e02a
```

## Q2. Log into the Bender account!
![](./screenshots/06.png) <br>
![](./screenshots/07.png) <br>

```
bender@juice-sh.op'-- 
```
### Flag
```
fb364762a3c102b2db932069c0e6b78e738d4066
```

# [Task 4] Who broke my lock?!

## Q1. Bruteforce the Administrator account's password!
Send the request to Intruder. <br>
![](./screenshots/08.png) <br>

Click on the `Intruder` tab.
![](./screenshots/09.png) <br>
Select the Clear `§` button. In the password field place two `§` inside the quotes. <br>
![](./screenshots/10.png) <br>
For payload, we need to install this first. <br>
```bash
apt-get install seclists
```
![](./screenshots/11.png) <br>

After installtion completed, load the wordlist from the location ` /usr/share/wordlists/SecLists/Passwords/Common-Credentials/best1050.txt`. <br>

![](./screenshots/12.png) <br>
Then `Start Attack`. <br>
![](./screenshots/13.png) <br>

Waiting until the attack finished. <br>
![](./screenshots/14.png) <br>

You can see the progress beneath. <br>
![](./screenshots/15.png) <br>


---

# Reference
- [TryHackMe : OWASP Juice Shop](https://ex0a.medium.com/tryhackme-owasp-juice-shop-53e87fb1af36) by Emre Alkaya, 2020.
- [Burp Suite and Foxy Proxy Setup](https://medium.com/@DatBoyBlu3/burp-suite-and-foxy-proxy-setup-67d5c1d86f8c) by Daniel Edwards, 2023.
