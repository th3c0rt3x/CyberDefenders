
I will try to run walk-through using simple methods not with indepth tools.

Tools Used 
  - 7-Zip 32 bit
  - Notepad++ 32 bit
  - Forensic 7z plugin https://www.tc4shell.com/en/7zip/forensic7z/

Just extract the zip file using 7-zip or your preffered zip tools and verify the check sum.

Since I am usng old latop which can't be instaled with FTK or some other disk forensics tool, I prefer to working to alternate tools which can works on Win 7 32 bit.

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
