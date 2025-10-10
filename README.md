# networking-cybersecurity-interview-cheatsheet
[![Update](https://img.shields.io/badge/status-active-success.svg)]()
[![Stars](https://img.shields.io/github/stars/yourname/interview-cheatsheet.svg?style=social)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)]()

## Introduction
**You don’t need to master everything — you just need to understand the basic fundamentals.**  
That’s the real key to interviews in both network  and cybersecurity related roles, two broad and ever-evolving fields

As wise Einstein once said: **If you can't explain it simply, you don't understand it well enough**

Specialization will come with your company training and experience.  
Right now, your goal is to show that you *get the bigger picture.*

This guide collects:
- Essential networking and cybersecurity concepts  
- Simple tricks and mental models to remember them  
- Real interview questions I’ve been asked throughout my journey  

Use it to review, refresh, or prepare — fast/effective.

## Contents

- [Core Networking](#core-networking)
- [Security Fundamentals](#security-fundamentals)
- [Tools & Commands](#tools--commands)
- [Scenarios](#scenarios)
- [Study Plan](#study-plan)


Operating systems:

1. i learned journalctl for logs, and how to use it to specifically check for certain logs, certain times as well
2. learner the useradd and add user, how to add users basically and log files for them
3. Root User has all access in linux
   
General networking:

1. The DNC DHCP and NAT services are provided by my rooter
2. DNS can help but if not there then i can refer to everything by ip
3. NAT takes place when it comes to helping the network go to the internet as one outside ip
4. Mask is basically a way to tell which part of the ip is important
5. TCP is a 3 way hanshake (sending responding confirming)
6. All people seem to need data processing (application, presentation, session, transport, network, data-link, physical)
7. UDP is not as reliable as TCP but faster
8. HTTP lives on top of tcp, it sends the data using the connection tcp made, HTTP handles what the dada mean
9. TLS is in between the HTTP and TCP, primary role is to encrypt the data
10. ARP is translating mac to ip while DNS is ip to name
11. vlan is groups of devices connected
12. TLS is what differentiates http from https 
13. In order for the device to find its first ip it sends a broadcast for the dhcp to reply with an ip
14. Bridged lan gives an ip to the device in the network belonging to same lan as the network
15. Ras is the communication protocol that makes vpns work
16. DHCP gives the DNS server so the DNS doesn't need to broadcast

OSI PROTOCOLS:

HTTP: application layer 7, it gives meaning to data, how to appear
DNS: application layer 7, even though it does handle ips its actually layer 7 on top of tcp
Ip: network Layer 3, of course its network layer its the adress of each device. 
Ethernet: data-link layer 2. Layer 2 is where the connection from mac to mac happens, its there.
SSH: application layer 7, again runs on top of tcp so it cant be lower 
ICMP: network layer 3, it's used for pings that help network diagnosis
FTP: Application layer 7, needs tcp to function
TLS: Presentation layer 6, between the http and tcp to encrypt-decrypt


According to nist:
Detect: Spot unusual or malicious activity.
Analyze: Confirm and understand the threat.
Contain: Isolate affected systems.
Eradicate: Remove the threat completely.
Recover: Restore normal operations safely.
Learn & Improve: Review and strengthen defenses.
Scenario:
When I enter goolge.com for the first time
1. DNS resolution, device is asking for googles ip adress in order to reach it
2. With that ip now i can set tcp, a 3 way handshake between the device and google
3. Since we are in https TLS takes place to secure and encrypt data
4. http request now to see the page google got
5. Server processing to load anything it needs
6. Google will send back the nessesary things
7. Rendering the data to display it
8. Cashing what ever is allowed for faster time

Questions:
1) hashing VS encryption
Hashing: It's only to prove integrity of a file, changes with every detail changed
Encryption: only people with a key can read a message

Got asked:
udp-tcp
type of attacks
docker-linux commands
ports
vlan
where to see logs

Computers over a network:
A device is different from a user. When you try to register a new device to the domain, you need to firstly create another user (the starting boot user) and then join the device to the domain. By doing that you can actually sign out and of course with the pre created user in domain controller-active directory you will be able to sign and also see the device as an object in active directory you can also add in a group of you linking. Pinging is a device related thing. You can always ping a device in the network but the user may not be accepted. 




# Cybersecurity & Networking Interview Cheat Sheet
[![Update](https://img.shields.io/badge/status-active-success.svg)]()
[![Stars](https://img.shields.io/github/stars/yourname/interview-cheatsheet.svg?style=social)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)]()

## Contents
- [Core Networking](#core-networking)
- [Security Fundamentals](#security-fundamentals)
- [Tools & Commands](#tools--commands)
- [Scenarios](#scenarios)
- [Study Plan](#study-plan)

<details><summary><b>TCP vs UDP (cheat table)</b></summary>

| Feature | TCP | UDP |
|---|---|---|
| Connection | Yes | No |
| Reliability | High | Best-effort |
| Use cases | HTTP/S, SSH | DNS, VoIP |

</details>

> **Tip:** Memorize the 5-tuple (src/dst IP, src/dst port, protocol) for packet filters.


# Cybersecurity & Networking Interview Cheat Sheet

Short one-liner about who this is for (SOC, NetEng, SecEng, blue team) and how to use it in the last week before interviews.

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![License](https://img.shields.io/badge/license-MIT-informational.svg)]()

## Contents
- [Core Networking](#core-networking)
- [Security Fundamentals](#security-fundamentals)
- [Protocols & Ports](#protocols--ports)
- [Tools & Commands](#tools--commands)
- [Linux/CLI Essentials](#linuxcli-essentials)
- [Cloud & Zero Trust Basics](#cloud--zero-trust-basics)
- [Common Interview Q&A](#common-interview-qa)
- [Scenarios & Troubleshooting](#scenarios--troubleshooting)
- [Study Plan (7 Days)](#study-plan-7-days)
- [References](#references)

## Core Networking
- **OSI vs TCP/IP**: quick contrast table + when each is used.
- **Routing & Switching**: ARP, STP, VLANs, NAT, subnetting mini-table.

## Security Fundamentals
- **CIA triad / AAA**, threat vs vuln vs risk, risk mgmt (likelihood × impact).
- **AuthN vs AuthZ**, least privilege, segmentation/microseg.

## Protocols & Ports
| Service | Port | Notes |
|---|---:|---|
| DNS | 53/UDP,TCP | recursion, zone transfer |
| HTTP/S | 80/443 | HTTP/2 basics, TLS handshake bullets |
| SSH | 22 | key auth, agent fwd risks |

## Tools & Commands
### nmap


QUIZ: https://quizlet.com/231268221/general-information-security-questions-flash-cards/
SANS Cheat Sheets: https://www.sans.org/blog/the-ultimate-list-of-sans-cheat-sheets/
Offensive Security (OSCP): https://411hall.github.io/OSCP-Preparation/
https://medium.com/@falconspy/oscp-exam-attempt-1-1893df5a0a00
VulnHub - LABS: https://www.vulnhub.com/

