I will try to run walk-through using simple methods not with indepth tools.

Tools Used 
  - 7-Zip 32 bit
  - Notepad++ 32 bit
  - Couple of OSINT Tools (mostly online based)
  
Topics
  - OSINT
  - Steganography
  - Passive Web Enumeration

Just extract the zip file using 7-zip or your preffered zip tools and verify the check sum of eachfiles.


Learn the basics of gathering information related to websites using open source intelligence research with this fantastic challenge.

Challenge looks like mixed version of online OSINT challenges. I will add couple of track back url's related to tools and old challenges which are added to current challenge.

```diff
+ NOTE : I will Try to update this page upon my free time.
```

### 1	  File->Vehicle-number.png: At which minute of the video was the vehicle observed?

We need to play the video LV.MP4 and watch when did the vechile appeared .


after watching the 37 minitues videos the number plated car started appearing at 35:33 and we can have clear visibility of number plate at last few seconds of the video. (36:50 to 37:03).

![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_1_1.png)

266LYK license plate is registered to a 2013 TOYOTA SCION tC in Nevada state. (Source: https://findbyplate.com/US/NV/266LYK/)


```diff
+ Flag : 35
```


### 2	  File->Vehicle-number.png: At which minute of the video was the vehicle observed?

Lets again quick look at video at 35:33 we saw vechile and number became visible on 36:07.

lets check the known locations near the area where we observed the car's enroute to.

![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_2_1.PNG)

By above Image its clear that the video took at Nevada, US.

![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_2_2.PNG)

* El Cortez Casino

Lets Search for "El Cortez Nevada" where Google route me to this URL 
https://en.m.wikipedia.org/wiki/El_Cortez_(Las_Vegas)

![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_2_3.PNG)


```diff
+ Flag : 89101
```



### 3	  File->Chapel: This chapel has a live webcam. What is the name of the chapel?

Look at video especial 27:20 where can get the same pic from video. lets check for "Live Cams NV US"  lead to earthcams.com where we just search for Chapel NV.

https://www.earthcam.com/search/ft_search.php?term=Chapel+NV

![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_3_1.PNG)

The chapel's name is Elvis Wedding Chapel

```diff
+ Flag : Elvis Wedding Chapel
```



### 4	  File->Chapel: What strip hotel does the chapel have a view of?

Use Google Maps Streetview to find the view and name of the hotel. Lets search for "Elvis Wedding Chapel"

https://www.google.com/maps/search/Elvis+Wedding+Chapel/@36.1478021,-115.154467,16z

![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_4_1.PNG)

https://www.google.com/maps/d/viewer?msa=0&ie=UTF8&t=h&ll=36.14660487818913%2C-115.15606554973755&mid=1JEkfH9bJtMKrVCMHrKGPP_QmMys&z=18 (9th PIC from street view)

![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_4_2.PNG)

as per street view The STRAT Hotel, Casino & SkyPod hotel has view of Chapel

```diff
+ Flag : The STRAT (looks like Flag is CaseSensitive)
```


### 5	  What date did the Mandalay Bay shooting take place?

Just ask same Question to Google

![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_5_1.PNG)

```diff
+ Flag : 01/10/2017
```


### 6	  On 30/09/2017 at 14:47, Stephen Paddock was seen on CCTV footage. Where was he?

*Stephen Paddock* Who is he :interrobang:

Lets search who is this *Stephen Paddock* (Since I am from native india I did not follow much news about US Region) 

Ooh no I could not explain how feels when I look at google about this man, 

https://en.wikipedia.org/wiki/Stephen_Paddock I am not going to explain anything relates to this Question try to solve directly lets look at the videos youtube https://www.youtube.com/watch?v=6ZRgVX8SYX4
or WT Post https://www.washingtonpost.com/news/post-nation/wp/2018/05/02/las-vegas-police-release-video-footage-recorded-inside-gunman-stephen-paddocks-hotel-suite/

If you watch the above videos the said guy is showed at Elevator

```diff
+ Flag : Elevator
```



### 7	  File->Vehicle.png: This vehicle may be related to our investigation. What place did it go to?

Lets Check the last 10 mins of the video, about from 29th minute to 31st mins its been passed to couple of buildings and places 


![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_7_1.PNG)

where we can able to observe


![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_7_2.PNG)


![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_7_3.PNG)


![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_7_5.PNG)

On next to road yellow color vechile is placed at Tux & Gown (30:56)

```diff
+ Flag : Tux & Gown
```



### 8	  Find MGM financial report in the form of a PDF document (not website) which contains the words: 'Consolidated net revenues increased 13% compared to the prior-year quarter to $3.2 billion' Submit the URL as an answer.

Let use Google dork for  'MGM "Consolidated net revenues increased 13% compared to the prior-year quarter to $3.2 billion" type:pdf'


![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_8_1.PNG)

http://q4live.s22.clientfiles.s3-website-us-east-1.amazonaws.com/513010314/files/doc_financials/quarterly/2019/q2/Q2-2019-ER-FINAL-(006).pdf

```diff
+ Flag : http://q4live.s22.clientfiles.s3-website-us-east-1.amazonaws.com/513010314/files/doc_financials/quarterly/2019/q2/Q2-2019-ER-FINAL-(006).pdf
```


### 9	  File->Number: What is the complete number?

Let look at video inbtw 33:00 to 31:00


![](https://github.com/th3c0rt3x/CyberDefenders/blob/main/c52-CaseVegas/c52_9_1.PNG)

Check google map history or extract the number from the video. The number is 702-735-5700.


```diff
+ Flag : 702-735-5700
```

*last updated on 0:01:20.05 A.M. IST*


### 10	  File->Number: Who is the number's owner?

```diff
+ Flag : 
```


### 11	  What is the MAC address of Desert Star WIFI?

```diff
+ Flag : 
```


### 12	  What is New York-New York?

```diff
+ Flag : 
```


### 13	  What is New York-New York?

```diff
+ Flag : 
```


### 14	  File->Devil.png: What does this belong to? The Devil is in the detail. Provide the tower name.

```diff
+ Flag : 
```


### 15	  At which minute of the video was The Deuce (Las vegas bus) observed?

```diff
+ Flag : 
```


### 16	  At which minute of the video was The Deuce (Las vegas bus) observed?

```diff
+ Flag : 
```


### 17	  The sign at 36.131749, -115.164647 is advertising what show?

```diff
+ Flag : 
```


### 18	  Files->Person-2: At which minute of the video did you see this person?

```diff
+ Flag : 
```


### 19	  Facebook ID 250240925003365 is linked to a criminal group. What are they called?

```diff
+ Flag : 
```


