
I will try to run walk-through using simple methods not with indepth tools.

Tools Used 
  - 7-Zip 32 bit
  - Notepad++ 32 bit
  - Forensic 7z plugin https://www.tc4shell.com/en/7zip/forensic7z/

Just extract the zip file using 7-zip or your preffered zip tools and verify the check sum.

Since I am usng old latop which can't be instaled with FTK or some other disk forensics tool, I prefer to working with alternate tools which works on my Win 7 32 bit machine.

As discussed earlier I will be using Forensic 7z Plug-in for extracting ad1 image tc4shell has tutorial how to install plugin.

![Image of 7z Extension](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c46-FirstHack/c46_1.PNG)


We will go through with one by one

## 1  What distribution of Linux is being used on this machine? 
  Lets look into kern.log file where we can able to find the distribution of Linux image
  
  ```
  Mar 21 18:53:38 KarenHacker kernel: [    0.000000] random: get_random_bytes called from start_kernel+0x3d/0x456 with crng_init=0
Mar 21 18:53:38 KarenHacker kernel: [    0.000000] Linux version 4.13.0-kali1-amd64 (devel@kali.org) (gcc version 6.4.0 20171026 (Debian 6.4.0-9)) #1 SMP Debian 4.13.10-1kali2 (2017-11-08)
Mar 21 18:53:38 KarenHacker kernel: [    0.000000] Command line: BOOT_IMAGE=/boot/vmlinuz-4.13.0-kali1-amd64 root=/dev/sda5 ro initrd=/install/gtk/initrd.gz quiet
```
### Flag : kali
![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c46-FirstHack/c46_1A.PNG)
## 2  What is the MD5 hash of the apache access.log? 
  Let go with 7-Zip Utility where can able to find the md5 has of access.log which is located at 
  
  ```
  Name: Horcrux.E01:Partition 5 [14304MB]:NONAME [ext4]\[root]\var\log\apache2\
  ```
  ![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c46-FirstHack/c46_2A.PNG)
### Flag : D41D8CD98F00B204E9800998ECF8427E
![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c46-FirstHack/c46_2A_1.PNG)

## 3 It is believed that a credential dumping tool was downloaded? What is the file name of the download? 
  As you are Forensic analyst you should be anayzing the download folders most of the downloads are at users to Downloads location, when we observe the ad1 image which has only 3 folders /root /boot /var
  ### Flag : mimikatz_trunk.zip
 ![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c46-FirstHack/C46_3A.PNG)
  
## 4  There was a super-secret file created. What is the absolute path? 
  Since the flag hint it self show as the super-secrect file is under /root folder, we will look int the files which are avaiable with /root folder, and I did get no luck with the .txt file under /root folder, at the same thought of check with bash_history where we can able to find the SuperSecrect File
```
systemctl status postgresql
systemctl enable postgresql
systemctl start postgresql
msfconsole
msfdb init
msfconsole
shutdown now
touch snky snky > /root/Desktop/SuperSecretFile.txt
cat snky snky > /root/Desktop/SuperSecretFile.txt 
msfconsole 
clear
history
clear
history
whoami
hack
do hack
```
### Flag : /root/Desktop/SuperSecretFile.txt

## 5 What program used didyouthinkwedmakeiteasy.jpg during execution? 
clearly it was trick question which platform want to test your beginner skills where most if the programs which are been executed on attacker machine will be avail with .bash_history
```
sudo apt-get install moo
lol Castro just failed at all these commands. Someone pat him on the back. 
I tried okay
history > history.txt
binwalk didyouthinkwedmakeiteasy.jpg 
clear
history
exit
touch keys.txt
pwd
```
### Flag : binwalk

## 6  What is the third goal from the checklist Karen created? 
  Check List file is available at location /root/Desktop/Checklist
  ```
  Check List:

- Gain Bob's Trust
- Learn how to hack
- Profit
```
### Flag : Profit
## 7 How many times was apache run? 
 We earlier reviewed the apache access log to calculate its hash, and the eagle eyed forensicators among us may have noticed that the hash was ‘d41d8cd98f00b204e9800998ecf8427e’ which is the MD5 associated with a 0 byte file.

Reviewing the log directory, we find the same to be true of the other logs
![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c46-FirstHack/c46_7.PNG)
### Flag : 0

## 8  It is believed this machine was used to attack another. What file proves this? 
 While searching through the image, I was able to locate a screenshot within the /root/. This file is located at ‘/root/irZLAohL.jpeg’ 
 ![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c46-FirstHack/irZLAohL.jpeg)
 ### Flag : irZLAohL.jpeg
 
## 9  Within the Documents file path, it is believed that Karen was taunting a fellow computer expert through a bash script. Who was Karen taunting? 
This was bit tricy Question which takes much of your time. as per question karen is tauting with files under Documents file path, lets review .bash_history along with Documents file folder, we can observe there are couple of files available. lets look into what exactly these files consists of  
![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c46-FirstHack/c46_9.PNG)
File : bob.txt contains 0 bytes which indicate it does have nothing 
File : firstscript
```
pwd
ip route | grep default
netstat | grep 80
```
File : firstscript_fixed
```
echo "Showing you your current path"
pwd
echo "Show my default route"
ip route | grep --color default
echo "Show network connections w/ port 80"
netstat | grep --color 80
echo "Heck yeah! I can write bash too Young"
```
File : helloworld.sh
```
echo "hello world!"
```
after examining the firstscript_fixed file observed Yough is charm

### Flag : Young

## 10 A user su'd to root at 11:26 multiple times. Who was it?
  su events are recorded in the auth log at ‘/var/log/auth.log’, we can quickly parse this for events at that time using the following using notepad++ which we got below output:
 ```
 Line 1179: Mar 20 11:26:22 KarenHacker su[4060]: Successful su for postgres by root
	Line 1180: Mar 20 11:26:22 KarenHacker su[4060]: + ??? root:postgres
	Line 1181: Mar 20 11:26:22 KarenHacker su[4060]: pam_unix(su:session): session opened for user postgres by (uid=0)
	Line 1182: Mar 20 11:26:22 KarenHacker su[4060]: pam_systemd(su:session): Cannot create session: Already occupied by a session
	Line 1183: Mar 20 11:26:22 KarenHacker su[4060]: pam_unix(su:session): session closed for user postgres
	Line 1184: Mar 20 11:26:22 KarenHacker su[4074]: Successful su for postgres by root
	Line 1185: Mar 20 11:26:22 KarenHacker su[4074]: + ??? root:postgres
	Line 1186: Mar 20 11:26:22 KarenHacker su[4074]: pam_unix(su:session): session opened for user postgres by (uid=0)
	Line 1187: Mar 20 11:26:22 KarenHacker su[4074]: pam_systemd(su:session): Cannot create session: Already occupied by a session
	Line 1188: Mar 20 11:26:22 KarenHacker su[4074]: pam_unix(su:session): session closed for user postgres
	Line 1189: Mar 20 11:26:22 KarenHacker su[4081]: Successful su for postgres by root
	Line 1190: Mar 20 11:26:22 KarenHacker su[4081]: + /dev/pts/0 root:postgres
	Line 1191: Mar 20 11:26:22 KarenHacker su[4081]: pam_unix(su:session): session opened for user postgres by (uid=0)
	Line 1192: Mar 20 11:26:22 KarenHacker su[4081]: pam_systemd(su:session): Cannot create session: Already occupied by a session
	Line 1193: Mar 20 11:26:22 KarenHacker su[4081]: pam_unix(su:session): session closed for user postgres
	Line 1194: Mar 20 11:26:22 KarenHacker su[4094]: Successful su for postgres by root
	Line 1195: Mar 20 11:26:22 KarenHacker su[4094]: + /dev/pts/0 root:postgres
	Line 1196: Mar 20 11:26:22 KarenHacker su[4094]: pam_unix(su:session): session opened for user postgres by (uid=0)
	Line 1197: Mar 20 11:26:22 KarenHacker su[4094]: pam_systemd(su:session): Cannot create session: Already occupied by a session
	Line 1198: Mar 20 11:26:22 KarenHacker su[4094]: pam_unix(su:session): session closed for user postgres
	Line 1199: Mar 20 11:26:22 KarenHacker su[4101]: Successful su for postgres by root
	Line 1200: Mar 20 11:26:22 KarenHacker su[4101]: + /dev/pts/0 root:postgres
	Line 1201: Mar 20 11:26:22 KarenHacker su[4101]: pam_unix(su:session): session opened for user postgres by (uid=0)
	Line 1202: Mar 20 11:26:22 KarenHacker su[4101]: pam_systemd(su:session): Cannot create session: Already occupied by a session
	Line 1203: Mar 20 11:26:23 KarenHacker su[4101]: pam_unix(su:session): session closed for user postgres
	Line 1204: Mar 20 11:26:23 KarenHacker su[4114]: Successful su for postgres by root
	Line 1205: Mar 20 11:26:23 KarenHacker su[4114]: + /dev/pts/0 root:postgres
	Line 1206: Mar 20 11:26:23 KarenHacker su[4114]: pam_unix(su:session): session opened for user postgres by (uid=0)
	Line 1207: Mar 20 11:26:23 KarenHacker su[4114]: pam_systemd(su:session): Cannot create session: Already occupied by a session
	Line 1208: Mar 20 11:26:23 KarenHacker su[4114]: pam_unix(su:session): session closed for user postgres
  ```
  ### Flag : postgres

## 11  Based on the bash history, what is the current working directory? 
 while examine bash history, reviewing the last cd to an absolute path we see that the user changed directory to /root. Thereafter we can review the following cd commands to see what impact they would have on the current working directory.
 ```
 Line 9: touch snky snky > /root/Desktop/SuperSecretFile.txt
Line 10: cat snky snky > /root/Desktop/SuperSecretFile.txt 
Line 69: cd ../root/Documents/myfirsthack/../../Desktop/
```
### Flag : /root/Documents/myfirsthack/
