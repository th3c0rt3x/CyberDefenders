I will try to run walk-through using simple methods not with indepth tools.

Tools Used 
  - 7-Zip 32 bit
  - Notepad++ 32 bit
  - Forensic 7z plugin https://www.tc4shell.com/en/7zip/forensic7z/
  - Eric Zimmerman's Tools
  - Prefetch Viewer from NirSoft Forensic Tools
  - DB Browser for SQLite
  - DCode Tool https://www.digital-detective.net/dcode/
  - Volatility 3
  

Just extract the zip file using 7-zip or your preffered zip tools and verify the check sum.

Since I am usng old latop which can't be instaled with FTK or some other disk forensics tool, I prefer to working with alternate tools which works on my Win 7 32 bit machine.


Lets walk-through one by one

Lets Unzip c49-Africanfalls2.zip and find what has init.

```
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-----        17-06-2021  20:30:39 4831838208 20210430-Win10Home-20H2-64bit-memdump.mem
```

Zip file consists of Win10home Memory dump for which we have solved couple of questions based on previous AfricanFall challenge

Lets try to examine the Memory dump usnig volatility framework irrespective of version ;), Lets try to get some basc inforamation about Image.




## 1	 What time was the RAM image acquired according to the suspect system? (YYYY-MM-DD HH:MM:SS) 


```diff
+ Flag : 
```
<hr>

## 2	  What is the SHA256 hash value of the RAM image? 


```diff
+ Flag : 
```
<hr>


## 3	 What is the process ID of "brave.exe"? 



```diff
+ Flag :
```

## 4	 How many established network connections were there at the time of acquisition? (number) 

```diff
+ Flag :
```


## 5	   What FQDN does Chrome have an established network connection with? 



```diff
+ Flag : 
```

## 6	  What is the MD5 hash value of process memory for PID 6988? 



```diff
+ Flag : 
```

## 7	  What is the word starting at offset 0x45BE876 with a length of 6 bytes? 

```diff
+ Flag : 
```

## 8	  What is the creation date and time of the parent process of "powershell.exe"? (YYYY-MM-DD HH:MM:SS) 

```diff
+ Flag : 
```

## 9	  What is the creation date and time of the parent process of "powershell.exe"? (YYYY-MM-DD HH:MM:SS) 
```diff
+ Flag : 
```

## 10	 How long did the suspect use Brave browser? (hh:mm:ss) 

```diff
+ Flag : 
```

<hr>

### References

Command Ref : https://github.com/volatilityfoundation/volatility/wiki/Command-Reference
Vol 3 Package : https://volatility3.readthedocs.io/en/latest/volatility.html#subpackages

