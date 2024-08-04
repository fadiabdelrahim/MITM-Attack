# MITM Attack 

##Introduction

The rise of digital communication and the reliance on networked systems have made cybersecurity a critical aspect of modern computing. Man-in-the-Middle (MITM) attacks, where an attacker secretly intercepts and possibly alters communication between two parties, represent a significant threat to data integrity and privacy. This project aims to explore the intricacies of MITM attacks through the use of Ettercap, a powerful tool for conducting these types of attacks. By setting up a rogue access point (AP) and executing a MITM attack, this report delves into the step-by-step process of launching and managing the attack, the challenges faced, and the critical lessons learned regarding network security.

## Choice of a Rogue AP setup

***Etttercap***
- Ettercap is a comprehensive suite for man-in-the-middle attacks. It features sniffing of live connections and content filtering. It supports active and passive breakdown of many protocols and includes many features for network and host analysis.

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
- Start Ettercap in graphical mode using the command sudo ettercap -G
