***DISCLAIMER:*** *This is intended for ethical hacking educational purpose. Performing hacking attempts on computers that you do not own (without permission) is illegal! Do not attempt to gain access to devices that you do not own!*

# <div align="center">MITM Attack</div>

## Introduction

The rise of digital communication and the reliance on networked systems have made cybersecurity a critical aspect of modern computing. Man-in-the-Middle (MITM) attacks, where an attacker secretly intercepts and possibly alters communication between two parties, represent a significant threat to data integrity and privacy. This project aims to explore the intricacies of MITM attacks through the use of Ettercap, a powerful tool for conducting these types of attacks. By setting up a rogue access point (AP) and executing a MITM attack, this report delves into the step-by-step process of launching and managing the attack, the challenges faced, and the critical lessons learned regarding network security.

## Choice of a Rogue AP setup

***Etttercap***
Ettercap is a comprehensive suite for man-in-the-middle attacks. It features sniffing of live connections and content filtering. It supports active and passive breakdown of many protocols and includes many features for network and host analysis.

***Why Ettercap?***

- ***Versatility and Compatibility:*** Works seamlessly across various network topologies and protocols, making it ideal for intercepting.
- ***User-Friendly GUI:*** Has a user-friendly graphical interface (GUI), simplifying setting up and executing attacks.

## Emulation Setup

- ***Initiating Ettercap:*** Launched Ettercap on the Kali VM and selected the appropriate network interface.
- ***Target Selection:*** Utilized Ettercap host scanning feature to identify the IP address of the target Windows VM
- ***ARP Poisoning Attack:*** Configured and executed an ARP poisoning attack targeting the Windows VM to intercept the traffic between the Windows VM and the network.
- ***Credential Interception:*** Accessed “vulnweb.com”, selected a vulnerable website from the Windows VM, and entered mock credentials for the login process. Next, I monitored the Ettercap console on the Kali VM for the credentials transmitted in plain text over HTTP.

## Step-by-Step Deployment

***Launch Ettercap
<div align="center">Start Ettercap in graphical mode using the command sudo ettercap -G</div>
<p align="center"><img src=images/Picture1.png></p>

---

***Selecting the Network Interface***
<div align="center">Select the network interface connected to the local network</div>
<p align="center"><img src=images/Picture2.png></p>
<p align="center"><img src=images/Picture3.png></p>

---

***Scanning for Hosts***
<div align="center">Use the “Host” list to scan for available devices on the network</div>
<p align="center"><img src=images/Picture4.png></p>
<p align="center"><img src=images/Picture5.png></p>
<p align="center"><img src=images/Picture6.png></p>

<div align="center">Added the gateway to Target1 and the victim IP to Target2</div>
<p align="center"><img src=images/Picture7.png></p>
<p align="center"><img src=images/Picture8.png></p>
<p align="center"><img src=images/Picture9.jpg></p>

---

***ARP Poisoning***
<div align="center">Initiated ARP poisoning by selecting MITM menu</div>
<p align="center"><img src=images/Picture10.jpg></p>
<p align="center"><img src=images/Picture11.jpg></p>
<div align="center">Ensure “Sniff remote connections” is checked</div>
<p align="center"><img src=images/Picture12.jpg></p>

---

***Start Sniffing***
<div align="center">Begin to capture packets by clicking OK</div>
<p align="center"><img src=images/Picture13.jpg></p>
<p align="center"><img src=images/Picture14.jpg></p>

---

***View Captured data***
<div align="center">Select the Ettercap menu</div>
<p align="center"><img src=images/Picture15.jpg></p>
<div align="center">Select View option</div>
<p align="center"><img src=images/Picture16.jpg></p>
<div align="center">Select Profiles</div>
<p align="center"><img src=images/Picture17.jpg></p>
<p align="center"><img src=images/Picture18.jpg></p>
<div align="center">Access “vulnweb.com”, select a vulnerable website from the Windows VM, and entered mock credentials for the login process. Next, monitor the Ettercap console on the Kali VM for the credentials transmitted in plain text over HTTP.</div>
<p align="center"><img src=images/Picture19.jpg></p>

## Preventative Measures:
- ***Use HTTPS Always:*** Users should ensure they access websites over HTTPS, which encrypts the data in transit, making it significantly more difficult for attackers to intercept and decipher.
- ***Be Wary of Security Warnings:*** Do not ignore browser security warnings, especially those related to SSL certificates. These warnings can be indicators of an MITM attack in progress.
- ***Use VPN Service:*** A VPN can add an extra layer of encryption to your internet traffic, making it harder for attacker to perform successful MITM attacks.
- ***Keep Software Updated:*** Regularly update your browser and any security software. Updates often include patches for security vulnerabilities that could be exploited in MITM attacks.

## Conclusion

This project highlights the profound security risks posed by Man-in-the-Middle (MITM) attacks, particularly against unencrypted communication protocols. The use of Ettercap to perform these attacks underscores the vulnerabilities inherent in HTTP traffic and the critical importance of employing secure communication channels like HTTPS. Through the practical emulation of a MITM attack, this project has demonstrated how easily attackers can intercept and manipulate data when adequate security measures are not in place. The experience has reinforced the necessity of encryption, vigilant security practices, and the continuous updating of software to protect against such threats. 


## Full Disclaimer

Any action and or activities related to the material contained within this repository is solely your responsibility. The misuse of the tools and information in this repo could result in criminal charges being brought against the person in question. The author will not be held responsible in the event any criminal charges are brought against any individuals misusing the tools and information in this repository for malicious purpose or to break the law.
