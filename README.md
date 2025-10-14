# networking-cybersecurity-interview-cheatsheet-for beginers

## Introduction

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

### Linux
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

A **typical question** can look like this: 
> “What's the right group to add this user?”

💡 Understanding how **Active Directory** and **Domain Controllers** work shows interviewers that you grasp one of the most essential parts of corporate network management.

A## Actions and Permissions

Previously, we mentioned how **groups** help us manage many users at once.  
By adding users to a group, they automatically **inherit the policies and restrictions** assigned to that group.

Now, what kind of actions or restrictions can we actually apply to users?  
Let’s understand this through one of the most essential Linux commands: **`chmod`**.

### Understanding `chmod`

The `chmod` command (short for *change mode*) is used to modify file and directory permissions in Linux.  
It defines **who** can perform **what kind of actions** on a file.

Every file in Linux has three sets of permissions, each represented by three letters:

| Section | Who it applies to | Example |
|----------|------------------|----------|
| **u** (user) | The owner of the file | The person who created it |
| **g** (group) | Users in the same group as the owner | Team members or department |
| **o** (others) | Everyone else on the system | Any other user |

Each of these can have three types of access:
- **r** → Read (view the contents)  
- **w** → Write (edit or delete the file)  
- **x** → Execute (run the file if it’s a script or program)

### Example: `chmod rwx-rw-r--`

Let’s break it down:

| Section | Who | Permissions | Meaning |
|----------|------|--------------|----------|
| `rwx` | User (owner) | Read, Write, Execute | Full control over the file |
| `rw-` | Group | Read, Write | Can view and edit, but not execute |
| `r--` | Others | Read only | Can view the file but not modify it |

So in this example:
- The **owner** can do everything.  
- The **group** can read and modify.  
- **Others** can only read.

💡 The most important cybersecurity concept here is **limiting privileges** — never give more access than necessary.

A **key question** can be:
> “Write a Linux command to only allow the creator to read, write, and execute on this file.”


## Networks

We’ve mentioned networking several times already, but what exactly **is** networking — and how does it work?

Networking is the process of connecting computers and devices so they can communicate and share data.  
It relies on **protocols**, which act as the rules that define how information travels from one point to another.

### Protocols

A **protocol** is a predefined set of rules that determines how data is formatted, transmitted, and received across a network.  

Without protocols, one device’s “language” would be completely different from another’s.  
Protocols bring **order, structure, and compatibility** to digital communication.

Imagine a game of football — the game itself is networking, but without the rules (protocols), players wouldn’t know how to pass, score, or even start the match.


### Common Protocols and Concepts

💡 The only prerequisite to understanding these is knowing what an **IP address** and a **MAC address** are.

- **IP (Internet Protocol)**  
  An IP address is a unique numerical label assigned to each device on a network.  
  It identifies *where* a device is located so data can be sent to the correct destination — like a digital home address.

- **MAC (Media Access Control) Address**  
  A MAC address is a hardware identifier embedded in a device’s network interface card (NIC).  
  While IP addresses can change, a MAC address is permanent and unique to each device.

#### **DNS (Domain Name System)**
DNS translates human-readable domain names (like `google.com`) into IP addresses (like `142.250.190.78`).  
Without DNS, you would have to memorize IP addresses for every website you visit.

#### **ARP (Address Resolution Protocol)**
ARP is used to map an IP address to a physical MAC address on a local network.  
In simple terms, it helps devices find each other within the same network.

#### **DHCP (Dynamic Host Configuration Protocol)**
When you connect to a network, DHCP automatically assigns your device an IP address and provides other network details (like the DNS server and default gateway).  
It eliminates the need to manually configure each device.

#### **NAT (Network Address Translation)**
NAT allows multiple devices on a private network to share one public IP address when accessing the internet.  
It hides internal IPs and adds a layer of security by preventing direct access from outside.

#### **UDP (User Datagram Protocol)**
UDP sends data faster but without guaranteeing delivery.  
It’s used for applications where speed matters more than reliability — like video streaming, online gaming, or voice calls.

#### **TLS (Transport Layer Security)**
TLS provides encryption and authentication between two systems.  
It sits between HTTP and TCP, ensuring the data being sent is private and hasn’t been tampered with.

#### **HTTP / HTTPS (Hypertext Transfer Protocol / Secure)**
HTTP defines how web pages are transmitted between a client and a server.  
HTTPS is simply HTTP running over TLS — meaning it’s encrypted and secure.

### 💬 Fun Example — TCP vs UDP

To truly understand TCP, it helps to see its personality.

TCP cares about **delivery confirmation** — it keeps asking, “Did you receive it?”  
UDP, on the other hand, just sends the message and doesn’t care if you ever got it.

Here’s a perfect example from a popular networking joke online:

> **TCP/IP Joke:**  
> “Do you want to hear a joke about TCP/IP?”  
> “Yes, I’d like to hear a joke about TCP/IP.”  
> “Are you ready to hear the joke about TCP/IP?”  
> “I am ready to hear the joke about TCP/IP.”  
> “Here is a joke about TCP/IP.”  
> “Did you receive the joke about TCP/IP?”  
> “I have received the joke about TCP/IP.”  
> “Excellent. You have received the joke about TCP/IP. Goodbye.”

> **UDP Joke:**  
> “Here’s a joke about UDP… but I don’t care if you get it.”

This perfectly illustrates the difference:
- **TCP:** Reliable, connection-oriented, confirms delivery.  
- **UDP:** Fast, connectionless, doesn’t confirm anything.


### Protocol Summary Table

💡You can answer almost any multiple-choice question about protocols just by looking at this summary table.

| Concept | Full Name | Purpose |
|----------|------------|----------|
| **DNS** | Domain Name System | Converts domain names to IPs |
| **ARP** | Address Resolution Protocol | Maps IP addresses to MAC addresses |
| **DHCP** | Dynamic Host Configuration Protocol | Automatically assigns IPs to devices |
| **NAT** | Network Address Translation | Allows many devices to share one public IP |
| **UDP** | User Datagram Protocol | Fast, connectionless data transfer |
| **TLS** | Transport Layer Security | Encrypts communication between systems |
| **HTTP / HTTPS** | Hypertext Transfer Protocol (Secure) | Transfers web data (encrypted if HTTPS) |
| **IP** | Internet Protocol | Handles add

## Ports

All this networking wouldn’t be possible without **ports**.  
They are the specific entry and exit points through which data travels to and from applications on a device.

Imagine a house without doors — how would you enter or receive visitors?  
In the same way, without ports, computers wouldn’t know **where** to send or receive specific types of data.

Each port can be configured based on system or application needs,  
but some ports are **standardized** and recognized worldwide — these are known as **well-known ports**.

As we mentioned each device on a network is identified by an **IP address**, which tells *where* the device is located.
A single device can run many different services at once — web servers, email servers, remote access tools, and more.  
So, how does the network know **which service** the data should go to?

That’s where **ports** come in!

- The **IP address** identifies the **device**.  
- The **port number** identifies the **specific application or service** running on that device.

### Port Summary Table

| Port | Protocol | Service / Description |
|------|-----------|------------------------|
| **20 / 21** | FTP | File Transfer Protocol – transfer of files between systems |
| **22** | SSH | Secure Shell – encrypted remote access and file transfer |
| **25** | SMTP | Simple Mail Transfer Protocol – sending emails |
| **53** | DNS | Domain Name System – resolves names to IPs |
| **67 / 68** | DHCP | Dynamic Host Configuration Protocol – assigns IPs dynamically |
| **80** | HTTP | Web traffic (unencrypted) |
| **443** | HTTPS | Secure web traffic (HTTP over TLS/SSL) |
| **514** | Syslog (UDP/TCP) | Collects and forwards system and network logs |
| **3389** | RDP | Remote Desktop Protocol – remote graphical access to Windows systems |
| **8080** | HTTP (alternate) | Alternative web traffic port often used by proxy servers |

💡 Knowing these ports not only helps in interviews but also when analyzing traffic, troubleshooting connectivity, or identifying potential attacks during a network scan.

## OSI Model

We’ve talked about many protocols, ports, and policies — and all of them need to work **the same way across different systems**.  
That’s why the **OSI Model (Open Systems Interconnection)** was created:  
to standardize how different devices and software communicate, regardless of who built them.

So, the OSI model gives structure to your troubleshooting process — layer by layer.

### The Seven Layers of the OSI Model

| Layer | Name | Description | Example Protocols / Technologies |
|-------|------|--------------|----------------------------------|
| **7** | **Application** | Where users and applications interact with the network. | HTTP, HTTPS, DNS, FTP, SMTP |
| **6** | **Presentation** | Translates, encrypts, and compresses data so applications can understand it. | TLS/SSL, JPEG, MP3 |
| **5** | **Session** | Manages sessions (connections) between applications. | NetBIOS, RPC |
| **4** | **Transport** | Provides reliable or fast data delivery using TCP or UDP. | TCP, UDP |
| **3** | **Network** | Handles logical addressing and routing of packets. | IP, ICMP, ARP |
| **2** | **Data Link** | Responsible for node-to-node data transfer and MAC addressing. | Ethernet, PPP, VLANs |
| **1** | **Physical** | Deals with actual hardware transmission — cables, signals, and bits. | Ethernet cables, Fiber, Hubs |

### Why It Matters

It’s not only about making protocols compatible.  
The OSI model also helps us **troubleshoot**.

For example:
- If your **encryption** works but data doesn’t reach the destination, you might have a problem in the **transport** or **network layer**.  
- If your **application** won’t connect but the network is fine, the issue might be in the **application** or **presentation** layer.  

### How to Remember the Layers

A classic mnemonic (from Layer 7 → Layer 1):

> **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing

or in reverse (Layer 1 → Layer 7):

> **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way

A useful way to remember where each protocol belongs is to **think logically rather than memorize**.

Each protocol naturally fits into a layer based on what it does.

For example:
We previously said that **TCP** is responsible for creating the **connection** between two devices — so it must live **below** something like **HTTP**, which only works *after* a connection exists to send and receive data!  

So how can HTTP (which presents and transfers information) exist without TCP first establishing that reliable path?  
It can’t — that’s why HTTP is **above** TCP.

And how can TCP even function without **IP**, which provides the logical addressing that tells it where to send data?  
It can’t — so IP must be **below** TCP.

Finally, how could IP work if there was no **Ethernet cable or Wi-Fi signal** to actually move the bits?  
It couldn’t — that’s the **Physical Layer**.

💡 **Remember:** Don’t memorize the OSI model — **understand the logic behind it.**  
Every layer depends on the one below it to function.  
Learning to think in layers is one of the most powerful skills in networking and cybersecurity.

## Fundamental Protocols

There are a few **core protocols** that interviewers love to ask about.  
not because they’re random, but because they are the **foundation** of how all networks function.  

Let’s go a bit deeper into two of the most important ones: **TCP** and **DHCP**.
Which will also help you truly understand how communication actually happens in a network.

### **1. TCP (Transmission Control Protocol)**

**TCP** is one of the most critical protocols on the internet.  
It ensures **reliable, ordered, and error-checked delivery** of data between two devices.

You can think of TCP as the “guaranteed delivery service” of networking.  
Before any data is transferred, both sides must first agree to communicate — this is done using the famous **Three-Way Handshake**.

### **How TCP Works – The Three-Way Handshake**

When a client wants to connect to a server (for example, when your browser connects to `google.com`):

1. **SYN (Synchronize)** – The client sends a message asking to start a connection.  
2. **SYN-ACK (Synchronize-Acknowledge)** – The server replies saying “Got it, ready to connect.”  
3. **ACK (Acknowledge)** – The client confirms, and the connection is officially established.

At this point, data can flow in both directions **reliably**.

When the communication is done, a similar process (called the **four-way termination**) gracefully closes the connection.

💡 **Remember:** TCP sacrifices speed for **reliability**, ensuring every packet arrives in order and without errors.

### **2. DHCP (Dynamic Host Configuration Protocol)**

You may have noticed in the OSI model that there is no **DHCP**
DHCP deserves its own explanation because it works a bit differently than other protocols.
HERE LEFT!!

When a new device connects to a network, it doesn’t have an IP address yet.  
So how can it communicate with anything — especially before TCP even starts?

That’s where **broadcasts** come in.

### **How DHCP Works**

When you connect your laptop or phone to a Wi-Fi network:

1. **DHCP Discover** – Your device sends a *broadcast message* saying,  
   “Is there any DHCP server out there who can give me an IP?”  
2. **DHCP Offer** – The DHCP server replies with an available IP address and network details.  
3. **DHCP Request** – The client says “Yes, I’d like that one.”  
4. **DHCP Acknowledgment (ACK)** – The server confirms, and the device can now use that IP.

---

### **Why DHCP Doesn’t Use TCP**

TCP requires an IP address to create a connection in the first place —  
but DHCP’s job **is to assign that IP**.  
That’s why DHCP runs over **UDP** (ports **67** and **68**) instead of TCP.

UDP doesn’t require a connection setup, making it **faster and simpler** for these short, essential exchanges.

---

💡 **Key takeaway:**  
- **TCP** ensures data is delivered correctly once a connection exists.  
- **DHCP** helps create that connection in the first place by giving devices their IP configuration.




## Contents

- [Logs](#core-networking)
- [Security Fundamentals](#security-fundamentals)
- [Tools & Commands](#tools--commands)
- [Scenarios](#scenarios)
- [Study Plan](#study-plan)



MY NOTES: 

   
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

⭐ Found this useful? Star it to support beginner-friendly cybersecurity education!

