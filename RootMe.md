#THMlabs #Labs 
- For Local setup : [https://drive.google.com/file/u/0/d/1FIxBbgZWAjiCEqYRGXXrps8sfHqUmMQh/view?usp=sharing&pli=1](https://drive.google.com/file/u/0/d/1FIxBbgZWAjiCEqYRGXXrps8sfHqUmMQh/view?usp=sharing&pli=1)
1. Deploy the machine and check weather connected or not by `ping <TARGET_IP>`, if active the the *Task 01 is completed*.
2. Conduct a [[Nmap]] scan on the target machine with version scan `namp -sS -sV <TARGET_IP>`, then you get answers for *some questions of Task 02*
3. Once you get to to know the there is an **Apache Server** running on the machine then go on web browser and and open machine on browser. 
4. Then run [[Gobuster]] on the machine with either medium library or common one suggested is common as it has less wordlist and THM labs do get solved in this wordlists. You get the answer for last question of *Task 02* which is **/panel/**. 
5. Then you can go the `http//:<TRAGET_IP>/panel` there you find a php form so you can get a *reverse shell using php* then you can either get script from **Pentestmonkey** or from scripts folder in kali `/usr/share/dirb/wordlists/common.txt` then edit the IP where needed put **your IP as it if for reverse shell**.
6. Once you run [[Netcat]] on your terminal with specified port and the run the script by going into `http//:<TRAGET_IP>/uploads` then you get shell. 
7. Once you ls on user you find *user.txt* file on running you get the answer for *Task 03*.
8. Then now privilege Escalation and last task to get root access for last flag, If you see the hints you get a command to run `find / -user root -perm /4000` on running you find that python file as SUID bit enabled so if you go to [[gftobins]] by using *Hint 2* then you can find commands for privilege escalation using SUID bit just past it then you get root access you just have to `cd root` then you find root.txt and then ***ROOM IS SOLVED.*** 
