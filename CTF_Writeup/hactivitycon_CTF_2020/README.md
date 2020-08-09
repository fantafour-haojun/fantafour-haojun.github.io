# H@cktivityCon CTF 2020

The event was held from July 29th 12:00 PM PDT - July 31st, 12:00 PM PDT.

I particpated alone and managed to complete most of the Scavenger Hunt, some Warmups, Steganography, and Forensics. There are other challenges such as Binary Exploitation, Mobile, Internet of Things, Scripting, and Web as well.

I managed to finish at rank 574/3663 players
<img src="https://user-images.githubusercontent.com/54532620/89724705-19427c00-da39-11ea-8275-2a5ab1e4db76.JPG">

# Solutions
## Warmups

### CaesarMirror
Caesar caesar, on the wall, who is the fairest of them all?

Attached was a text file, the top part of what's given, the bottom part was that I have decipher before ROT13.
<img src="https://user-images.githubusercontent.com/54532620/89724718-4b53de00-da39-11ea-8d1f-0e15a91010fd.png">

What I did was ROT13 the first half of the text, the second half I reverse sentence by sentence followed by ROT13.

<img src="https://user-images.githubusercontent.com/54532620/89724748-c61cf900-da39-11ea-86f3-f0978630a326.png">

Joining the 3 section of the flag it will give you `flag{julius_in_a_reflection}`

### Common Place
```
asd7138: can you find the flag here?
tcm3137: no, i dont see it
jwh8163: i cant find it either
rfc5785: i found it
asd7138: what!? where?!
jwh8163: tell us!

Connect here:
http://xxxxx.com:50007
```

After searching rfc5785, it will lead you to http://xxxx.com:50007/.well-known/flag.txt.

### InternetCattos
The Internet is full of wonderful kittens and cattos. You can even find one at xxxx.com on port 50003!

I was using Chrome browser, so I just changed my browser to Firefox and the flag is shown.

### Hexgedit
Woah! Someone opened the flag file in hexedit... and then gedit??

<img src="https://user-images.githubusercontent.com/54532620/89724850-adf9a980-da3a-11ea-8772-26b5371b2791.png">

Use OCR to convert the image into text. Next convert the hex into text.

<img src="https://user-images.githubusercontent.com/54532620/89724857-d681a380-da3a-11ea-8f80-eaf5cfbeedfe.png">

### Private Investigator
We have hired you to help investigate this private key. Please use it to connect to the server like so:

ssh -i id_rsa user@xxxx.com -p 50004

When I ran the command with the id_rsa key file, there is an error stating that the file is not in the right format. Therefore with the given private key, throw the file in puttygen and re-generate the RSA private key.
<img src="https://user-images.githubusercontent.com/54532620/89724870-16488b00-da3b-11ea-93bb-f6e32e88da8a.png">

## OSINT
### World Hotspots
What can you tell me about 9C:EF:D5:FB:9F:F0?

With the help from my friend, the hint he gave was to use https://wigle.net/ and search the MAC address. After zooming into the spot the flag is right there.

<img src="https://user-images.githubusercontent.com/54532620/89724903-74756e00-da3b-11ea-8134-c9e01dad64e6.png">

## Forensics
### Opposable Thumbs - 75
The flag is right between your finger tips.

The attachement was a file named thumbcache_256.db

I tried using the thumbs viewer program to open up the file but it wasn't able to. Not sure why but seems like other players can do it.

I tried binwalk since I am out of ideas how to view this file.

<img src="https://user-images.githubusercontent.com/54532620/89724921-dd5ce600-da3b-11ea-9373-bb8fc17c248f.png">

Then I found this JPEG and I tried using this command `binwalk -D 'jpeg image:jpeg' thumbcache_256.db`

This jpeg image was indeed the flag.

<img src="https://user-images.githubusercontent.com/54532620/89724935-054c4980-da3c-11ea-8e46-93cdef2ae483.png">

## Scavenger Hunt
### Domo Arigato
The flag is found in the robots.txt of hackerone website.

### Million Dollar Jar of Mayo 
The flag is found in mayonaise hackerone profile page.

<img src="https://user-images.githubusercontent.com/54532620/89725163-3c702a00-da3f-11ea-9545-6c018e67ac3a.png">

### Like & Subscribe 
Upon visiting hackerone youtube about page, you will find the flag.

### Send me a flag and I'll double it
### Hawaii Five-0 
### The Finn'ishing Move
### The Founding Fathers
All of the challenges flags are found in the twitter page from different profile.

<img src="https://pbs.twimg.com/media/EeUTKjjVoAAhxiY?format=png">

### Flag Not Found
Trigger a file not found webpage and view page source to find the flag.


### Ride Share Disclosures
The clue was `Do you even lift, though?`

Found the flag from nahamsec disclosure page with Lyft.

<img src="https://pbs.twimg.com/media/EeUS6LuU0AAoaVT?format=png">


### \<a href="in"\>
This is the linkedin page of hackerone.

<img src="https://user-images.githubusercontent.com/54532620/89725062-c28b7100-da3d-11ea-9800-f709f8cd0608.png">

### Lights, Camera, Hacking!
It's the name of a youtube video uploaded by hackerone. Viewing the transcript you can see the flag.

<img src="https://user-images.githubusercontent.com/54532620/89725071-d33be700-da3d-11ea-925d-035c12b9c738.png">

### The Streamer
The flag was found in the hackerone twitch about tab.


### Security Report Powered by Hackers
### One of us
### _config.yml#35 

I was able to use the github code search and found these 3 flags.

<img src="https://user-images.githubusercontent.com/54532620/89724995-e0a4a180-da3c-11ea-9d1d-0be91ce27519.png">


### The Chosen One
The clue was NYC2017MVH which is one the Hackerone event.

### Hacker101 Discord
The flag is on the hackitivycon channel in hackerone discord at the title of iot-village.

### The Social Media Influencer
The flag is on the latest Hackerone instagram post.

### Pentesters Unite
Clue was `Hack2Learn`

I was able to login to the hackerone CTF platform and found the flag.

<img src="https://user-images.githubusercontent.com/54532620/89725010-1184d680-da3d-11ea-91c4-94a7f9d1b0d9.png">

### The Hacker101
Clue was `Is this CTF working?`

I was able to login to the hackerone CTF platform and found the flag.

<img src="https://user-images.githubusercontent.com/54532620/89725010-1184d680-da3d-11ea-91c4-94a7f9d1b0d9.png">

### Security@
This is the conference name organised by hackerone https://www.hackerone.com/security-at#:~:text=The%20only%20annual%20hacker%2Dpowered,elite%20hackers%20in%20the%20world.

Upon visiting the website of the conference, I search the page source and the flag is there.