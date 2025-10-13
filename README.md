# networking-cybersecurity-interview-cheatsheet-for beginers
[![Update](https://img.shields.io/badge/status-active-success.svg)]()
[![Stars](https://img.shields.io/github/stars/yourname/interview-cheatsheet.svg?style=social)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)]()

## 🧠 Introduction

**You don’t need to master everything — you just need to understand the fundamentals.**  
That’s the real key to interviews in both networking and cybersecurity — two broad, fast-evolving fields.

As Einstein wisely said: *“If you can’t explain it simply, you don’t understand it well enough.”*

Specialization will come with company training and hands-on experience.  
Right now, your goal is to show that you *grasp the bigger picture.*

**This guide collects:**
- Essential networking and cybersecurity concepts  
- Simple tricks and mental models to remember them  
- Real interview questions I’ve been asked throughout my journey  

Use it to review, refresh, and prepare — **fast and effectively.**



## Contents

- [Logs](#core-networking)
- [Security Fundamentals](#security-fundamentals)
- [Tools & Commands](#tools--commands)
- [Scenarios](#scenarios)
- [Study Plan](#study-plan)


## Logs

Logs are one of the most important topics in cybersecurity and networking.  
Whether you’re **troubleshooting a problem**, **investigating a threat**, or simply trying to **understand how something works** — logs are your best friend.

### What is a log?
A **log** is a recorded event — a timestamped message that describes something that happened on a system or network.  
Every device, service, and application generates logs: user logins, failed authentications, system errors, connections made, packets dropped, and so on.

They help answer questions like:
- Who did what, and when?  
- What failed or succeeded?  
- Is there something unusual happening?

**Example of a log entry:**

Oct 10 09:42:15 webserver sshd[1532]: Failed password for root from 192.168.1.45 port 51812 ssh2

## How to View Logs

There are many systems and tools that collect or manage logs
But in interviews, you usually won’t be asked to explain those in depth.  

A **very common question** is simply:
> “How do you view logs in Linux or Windows?”

This is a core question every candidate should be able to answer confidently — and it’s easy to practice yourself.

###  Windows
The built-in tool for viewing logs is **Event Viewer**, you can open it by simply searching for it from the Windows taskbar.
It lets you review **System**, **Security**, and **Application** logs in a structured way.


💡 Tip: You can filter logs by time, level (error/warning/info), or event ID.


### 🐧 Linux
Linux systems log events to files under `/var/log/` or through **systemd’s journal**.

The most common way to view logs on modern systems is with the **`journalctl`** command:

# View recent logs
journalctl -xe


### Log Management Concepts

Many companies that offer cybersecurity services typically set up a **SIEM** tool.  
If you understand how logs work, then you already understand the foundation of what a SIEM does.

**SIEM (Security Information and Event Management):**  

A SIEM collects, normalizes, and correlates logs from multiple sources (such as servers, firewalls,network devices).

It analyzes those logs in real time to detect suspicious behavior, generate alerts, and provide dashboards.

In simple terms:  
- **Logs** record what happens.  
- **SIEMs** connect and analyze those records to identify what matters.  

Another important tool related to logs is an **IPS**.  
If you understand how a SIEM works, you can easily grasp the concept of an IPS as well.

**IPS (Intrusion Prevention System):**  
An IPS monitors network traffic for signs of malicious activity or policy violations.

But Unlike a SIEM, it can take action! ( **block**, **reject**, or **quarantine** suspicious packets in real time). 


In short:
- **SIEM** — central brain analyzing logs from everywhere.  
- **IPS** — guards the network in real time.  

A **another common question** can simply be:
> “What's the difference between SIEM and IPS?”


## Responding to Detected Threats

When discussing tools that help us analyze logs and detect threats, a natural question arises:  
**What should we do if we actually detect a threat?**

**NIST (National Institute of Standards and Technology)**, a government agency that develops widely used frameworks and guidelines for cybersecurity has already answered that question with a general workflow that many companies follow.

Employers love to hear this, because it shows you understand the structured approach behind incident response.  

Even though the specific process may vary from one organization to another, these general principles apply everywhere.  
I highly suggest you learn this exactly as it is.

### According to NIST:

1. **Detect** – Spot unusual or malicious activity.  
2. **Analyze** – Confirm and understand the threat.  
3. **Contain** – Isolate affected systems to prevent further damage.  
4. **Eradicate** – Remove the threat completely.  
5. **Recover** – Restore normal operations safely.  
6. **Learn & Improve** – Review what happened and strengthen defenses for the future.


### Think of it as a story

To make it easier to remember, think of it like trying to deal with a bug flying around your house:

- You first **spot it** (Detect).  
- Then you **see what it is** — a harmless butterfly or a mosquito? (Analyze).  
- “Oh no, I just got bit!”  
- You **close the door** so it doesn’t escape (Contain).  
- You **kill it** (Eradicate).  
- You **treat the bite** with some cold water or cream (Recover).  
- And next time, you’ll be **faster and more prepared** (Learn & Improve).

Each concept in networking and cybersecurity — and even in life — can be simplified with a story.  
Don’t get lost in every technical detail!

💡 **Reminder:** Interviewers want to see that you understand the *bigger picture*.


## Domain Controller and Active Directory

Imagine working in a company with hundreds of employees.  
How do you manage what everyone can access, what permissions they have, and which devices belong to whom?  
That’s where **domains** and **Active Directory** come in.

### What is a Domain?
A **domain** is a networked environment where all users, computers, and resources (like printers or shared folders) are managed under a single set of rules and permissions.  
It allows centralized control — meaning you can manage everything from one place instead of configuring each computer individually.


### How Do You Manage a Domain?
The most common way to manage a domain in Windows environments is through **Active Directory (AD)**, which runs on a **Domain Controller (DC)**.


### What is Active Directory?
**Active Directory** is a directory service developed by Microsoft.  
It stores information about users, devices, and resources, and defines how they can interact with each other within the network.  
Think of it as a company-wide database of identities and permissions.

When someone logs in to a company computer, their credentials (username and password) are checked against the database inside Active Directory.  
If they match, access is granted.  
In most cases, the username is assigned by the administrator, while the user sets their password when they join the company.

### What Are Groups in Active Directory?
Groups are used to organize users and devices based on their roles or access needs.  
Instead of assigning permissions to each user individually, permissions are assigned to a **group**, and users inherit those permissions automatically.

For example:
- A “CEO” group might have access to confidential company files.  
- An “Interns” group might only access shared folders and basic tools.


### Users and Devices in AD
Each employee has both:
- A **user account**, which represents their identity.  
- A **device object**, which represents the computer they use.

When you connect a new device to the domain, it appears as an **object** in Active Directory.  
You then assign it to the correct group — for example, the CEO’s laptop goes to the “Executive Devices” group, while an intern’s workstation goes to the “Intern Computers” group.

This way, both **users and their devices** are organized and controlled centrally.

💡 Understanding how **Active Directory** and **Domain Controllers** work shows interviewers that you grasp one of the most essential parts of corporate network management.













MY NOTES: 

Operating systems:

2. learned the useradd and add user, how to add users basically and log files for them
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

