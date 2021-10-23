---
layout: post
title:  "Blog 5 - Wireshark"
date:   2021-10-22.
categories: jekyll update
---




<h1> Wireshark Commands </h1>


This week I would like to discuss some useful commands in wireshark and how to use them to view encrypted wireless WEP and WPA traffic.
The reason you need a type of encryption is because without it your traffic would be visable in plain text.
This means any usernames and passwords that you used to login to any websites would be viewable as plaintext and anyone listening to your 
traffic.

Now with WEP traffic if you have a captured .cap file you will not be able to view any of this traffic until you break the encryption.
To do this you will need to use a tool that is included with aircrack-ng suite, other tools included with this suite include airodump-ng, 
airmon-ng, aireplay-ng and many more.  For this we are just using the base aircrack-ng, because we already have a .cap file for us to use.
First you need to select the .cap file.
	aircrack-ng /tmp/captures/WEP1.cap

![WEP-1](https://v1ndl3r.github.io/CIT480/assets/WEP-1.PNG "WEP-1")

This will show you all wireless networks that are on this capture.  You need to know what network traffic that you are trying to view.
It will show you the BSSID, ESSID, and the Encyption, for this example we are attacking 5 TOWSON22 network. The software will attempt to 
brute-force the key after a small amount of time you will view this screen, which tells you that you have successfully found the key.

![WEP-2](https://v1ndl3r.github.io/CIT480/assets/WEP-2.PNG "WEP-2")

	AA:AA:AA:AA:AA


Now using this key we will decrypt the network traffic using that key and another security suite tool: airdecap-ng.
	airdecap-ng -w AA:AA:AA:AA:AA /tmp/captures/WEP1.cap

![WEP-3](https://v1ndl3r.github.io/CIT480/assets/WEP-3.PNG "WEP-3")
	

Now all the traffic is in plaintext and you can view usernames and passwords.
![WEP-4](https://v1ndl3r.github.io/CIT480/assets/WEP-4.PNG "WEP-4")

