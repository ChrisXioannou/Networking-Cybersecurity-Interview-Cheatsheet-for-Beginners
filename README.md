## **TOP PRIORITIES**

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


