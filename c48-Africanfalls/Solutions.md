I will try to run walk-through using simple methods not with indepth tools.

Tools Used 
  - 7-Zip 32 bit
  - Notepad++ 32 bit
  - Forensic 7z plugin https://www.tc4shell.com/en/7zip/forensic7z/
  - ShellBags Explorer from Eric Zimmerman's Tools
  - Prefetch Viewer from NirSoft Forensic Tools
  

Just extract the zip file using 7-zip or your preffered zip tools and verify the check sum.

Since I am usng old latop which can't be instaled with FTK or some other disk forensics tool, I prefer to working with alternate tools which works on my Win 7 32 bit machine.

As discussed earlier I will be using Forensic 7z Plug-in for extracting ad1 image (tc4shell has tutorial how to install plugin).

This respective challenge was designed to recall couple of techniques for investigator on below topics
* Browser Forensics
* Prefetch Forensics
* ShellBags 
* LOLBins


Lets walk-through one by one

Lets Unzip c48-Africanfalls.zip

![Initial zip](Zip.PNG)

![Disk Digger](Zip2.PNG)

## 1	What is the MD5 hash value of the suspect disk? 
Once you extract the zip file we can verify the checksum/md5 using couple of md5 tools or else we can find the txt file DiskDrigger.ad1.txt which contains the information about ad1 file

```
Created By AccessData® FTK® Imager 4.5.0.3 

Case Information: 
Acquired using: ADI4.5.0.3
Case Number: 
Evidence Number: 
Unique Description: 
Examiner: 
Notes: 


[Computed Hashes]
 MD5 checksum:    9471e69c95d8909ae60ddff30d50ffa1
 SHA1 checksum:   167aa08db25dfeeb876b0176ddc329a3d9f2803a

Image information:
 Acquisition started:   Tue Jun 15 12:28:20 2021
 Acquisition finished:  Tue Jun 15 12:33:10 2021
 Segment list:
  D:\Users\Mawso3a\Desktop\DiskDrigger.ad1

Image Verification Results:
 Verification started:  Tue Jun 15 12:33:18 2021
 Verification finished: Tue Jun 15 12:33:51 2021
 MD5 checksum:    9471e69c95d8909ae60ddff30d50ffa1 : verified
 SHA1 checksum:   167aa08db25dfeeb876b0176ddc329a3d9f2803a : verified

```

### Flag : 9471e69c95d8909ae60ddff30d50ffa1

## 2	 What phrase did the suspect search for on 2021-04-29 18:17:38 UTC? (three words, two spaces in between) 


## 3	 What is the IPv4 address of the FTP server the suspect connected to? 


## 4	 What date and time was a password list deleted in UTC? (YYYY-MM-DD HH:MM:SS UTC) 


## 5	 How many times was Tor Browser ran on the suspect's computer? (number only) 


## 6	 What is the suspect's email address? 


## 7	 What is the FQDN did the suspect port scan? 


## 8	 What country was picture "20210429_152043.jpg" allegedly taken in? 


## 9	 What is the parent folder name picture "20210429_151535.jpg" was in before the suspect copy it to "contact" folder on his desktop? 


## 10	 A Windows password hashes for an account are below. What is the user's password? Anon:1001:aad3b435b51404eeaad3b435b51404ee:3DE1A36F6DDB8E036DFD75E8E20C4AF4::: 


## 11	 What is the user "John Doe's" Windows login password? 

