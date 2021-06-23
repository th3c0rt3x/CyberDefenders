I will try to run walk-through using simple methods not with indepth tools. 

Before that we need to recall couple of filters usnig Wirehark. Below are couple of cheetsheets which are available freely online.
 
  - https://packetlife.net/media/library/13/Wireshark_Display_Filters.pdf
  - https://www.comparitech.com/net-admin/wireshark-cheat-sheet/
  - https://stationx-public-download.s3.us-west-2.amazonaws.com/Wireshark-Cheat-Sheet-v1.pdf

Tools Used 
  - 7-Zip 32 bit
  - Notepad++ 32 bit
  - NetworkMiner Free Edition https://www.netresec.com/?page=networkminer
  - DCode Tool https://www.digital-detective.net/dcode/
  - Couple of Online tools
	* qacafe previously known as CloudShark
	* https://www.cloudshark.org/captures/b801ff6bc08a
  

Just extract the zip file using 7-zip or your preffered zip tools and verify the check sum.

I prefer to working with alternate tools which works on my Win 7 32 bit machine.

This respective challenge was designed to recall couple of techniques for analyst on below topics
* PCAP Forensics
* Wireshark Filters


Lets walk-through one by one

Since its a 3rd part of the challenge for AfricanFalls which is on-going blue team challenge lets keep it simple.

Lets Unzip c50-AfricanFalls3.zip, after unziping the file we have got PCAP File **UNODC-GPC-001-003-JohnDoe-NetworkCapture-2021-04-29.pcapng**

Lets Open PCCANG file with well know Pcap anayzer WireShark

## PCAP Information
```
File

Name:
C:\Users\TheCortex\Desktop\tmp\c50-AfricanFalls3\UNODC-GPC-001-003-JohnDoe-NetworkCapture-2021-04-29.pcapng
Length:
38MB
Hash (SHA256):
3cc2061959afb116aeedce2736809f28236b96e20b89b4199194f4a30a0802ba
Hash (RIPEMD160):
e278720f93a6d58b45d1614877eb92b91ef0a684
Hash (SHA1):
0a40bcf2c2329ddf72bd864f05855314cb76514d
Format:
Wireshark/... - pcapng
Encapsulation:
Ethernet

Time

First packet:
2021-04-30 06:30:51
Last packet:
2021-04-30 06:38:21
Elapsed:
00:07:30

Capture

Hardware:
Intel(R) Core(TM) i7-10510U CPU @ 1.80GHz (with SSE4.2)
OS:
Linux 5.4.0-72-generic
Application:
Dumpcap (Wireshark) 3.2.3 (Git v3.2.3 packaged as 3.2.3-1)

Interfaces

Interface
Dropped packets
Capture filter
Link type
Packet size limit
wlo1
0 (0.0%)
none
Ethernet
262144 bytes

Statistics

Measurement
Captured
Displayed
Marked
Packets
45024
45024 (100.0%)
—
Time span, s
450.467
450.467
—
Average pps
99.9
99.9
—
Average packet size, B
821
821
—
Bytes
36965483
36965483 (100.0%)
0
Average bytes/s
82k
82k
—
Average bits/s
656k
656k
—
```

![PcapInfo](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c50-AfricanFalls3/PcapInfo.PNG)

Keep looking 
<hr>

## 1	

```diff
+ Flag : 
```
<hr>

## 2	 

```diff
+ Flag :   
```

<hr>

## 3	

```diff
+ Flag : 
```

## 4	 

```diff
+ Flag :
```


## 5	

```diff
+ Flag : 0
```

## 6	

```diff
+ Flag : 
```

## 7	

```diff
+ Flag : 
```

## 8	 
```diff
+ Flag : 
```

## 9	 

```diff
+ Flag : 
```

## 10	 

```diff
+ Flag : AFR1CA!
```

## 11	 

```diff
+ Flag : ctf2021
```