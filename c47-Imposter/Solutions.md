Since I am working with old laptop most of the tools where I am going to use to solve this challenge is based on Windows 7 / 32 bit tools, Since volatility depreciated the  support for 32 bit version I will be using volatility 2.5 and couple of tools from NIRSOFT.

## 1  What is the SHA1 hash of triage.mem (memory dump)? 
Try to calculate the hash of the file usnig any hash ckeck tools, I prefer to work with NirSoft hashMyFiles utility and its a smiple to use
![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c47-Imposter/c47_1_hash.PNG)
### Flag : c95e8cc8c946f95a109ea8e47a6800de10a27abd

## 2  What volatility profile is the most appropriate for this machine? (ex: Win10x86_14393) 
The first thing you’ll want to determine when analysing a memory image is it’s profile. We’ll need this for any on-going commands. There is a plugin called ‘imageinfo’ that will give you that data:
```
volatility.exe -f .\Triage-Memory.mem imageinfo

```
![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c47-Imposter/c47_2_ver.PNG)
### Flag : Win7SP1x64


## 3  What was the process ID of notepad.exe? 
pslist is a plugin that outputs all of the processes that were running at the time the dump was created, along with its execution time and process/parent ID’s.
```
volatility.exe -f .\Triage-Memory.mem --profile=Win7SP1x64 pslist | findstr notepad.exe
Where it gives output of notepad.exe pid

PS D:\CD\65\c47-Imposter> volatility.exe -f .\Triage-Memory.mem --profile=Win7SP1x64 pslist | findstr notepad.exe

0xfffffa80054f9060 notepad.exe            3032   1432      1       60      1      0 2019-03-22 05:32:22 UTC+0000
```
### Flag : 3032   
