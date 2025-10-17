# Day 1(DHCP)





# Day 2(NAT and PAT)

## NAT, PAT & Ports

### 1. What is NAT (Network Address Translation)?

* NAT is a technique that translates private IP addresses used inside a network into public IP addresses used on the Internet.
* It allows private networks (like home or office LANs) to access the Internet using limited public IPs.

* ***It helps in:***
   * Conserving public IPv4 addresses.
   * Hiding internal network details from the outside world (basic security).
   * Connecting multiple devices using one public IP.

 ### 2. Types of NAT

* ***Static NAT:***
    * One private IP ↔ one public IP (1-to-1 mapping).
    * Used for servers that need to be accessible from the internet (like a web or mail server).
    * *Example:*
     192.168.1.10 ↔ 203.0.113.10

* ***Dynamic NAT:***
    * Uses a pool of public IPs.
    * When a private host sends traffic, NAT dynamically assigns an available public IP.
    * Once the session ends, the IP returns to the pool.
    * *Example:* Pool: 203.0.113.5 to 203.0.113.9 → used by many internal hosts.

* ***PAT (Port Address Translation):***
     * Also called NAT Overload.
     * Multiple private IPs share one public IP.
     * Router differentiates connections by changing source port numbers.
     * Most common type — used in home routers.

### 3. How NAT Works (General Idea)  
* When a device (say, your laptop) sends a packet:  
> Source: 192.168.1.10  
> Destination: 142.250.195.78 (Google)

* The NAT device (your router) changes the source IP before sending it to the internet:   
> Source: 203.0.113.5 (public IP)   
> Destination: 142.250.195.78


When the reply comes back, NAT reverses the process using its internal translation table.

### 4. What Makes PAT Different

* PAT does the same thing as NAT but adds one more twist — it also translates port numbers.   

* ***Why?***
     * Because if many devices inside the LAN share one public IP, the router must ensure every session remains unique.
     * *Example:*
 
     |Inside Host|Private IP|Source Port|Translated IP|Translated Port| 
     |-----------|----------|-----------|-------------|---------------|
     |Laptop|192.168.1.10   |50000      |203.0.113.5	|40001  |
     |Mobile|192.168.1.11   |50000      |203.0.113.5 | 40002 |

Even though both used the same port internally, PAT made them unique by changing their source ports.

### 5. Why Does PAT Change Port Numbers?

* Because multiple internal devices can use the same source port at the same time.
* If the router didn’t change them, it couldn’t tell which reply belongs to which device.
* *PAT keeps a translation table like this:*

|Inside Local|Inside Global|Destination|Destination Port|
|------------|-------------|-----------|----------------|
|192.168.1.10:50000|203.0.113.5:40001|142.250.195.78|443|
|192.168.1.11:50000|203.0.113.5:40002|172.217.160.14|443|

When a reply comes to 203.0.113.5:40001, the router knows it belongs to 192.168.1.10:50000.

***So basically:***  
> NAT changes IPs  
> PAT changes IPs and ports to make every connection unique.

### 6. Which Port PAT Changes?
* Only the source port — never the destination port.
* ***Why?***
   * Destination port tells what service you’re requesting (like web, mail, etc.).
   * PAT doesn’t touch that because it would confuse the server.
   * PAT only changes source port to track each connection separately.

Example:
Before NAT:

Source: 192.168.1.10:50000 → Destination: google.com:443


After PAT:

Source: 203.0.113.5:40001 → Destination: google.com:443


Destination port (443) stays the same → the server still knows it’s a secure web request.

🧠 7. Role and Meaning of Port Numbers

Ports tell what kind of application/service the packet belongs to.

80 → HTTP (web)

443 → HTTPS (secure web)

25 → SMTP (mail)

53 → DNS

21 → FTP

👉 These are called well-known ports (0–1023).
When you type a URL like https://google.com, your computer automatically picks port 443.

So yes, you were absolutely right — ports tell your system and the server what kind of communication is happening.

💻 8. How Your Computer Chooses Source Port

Your device automatically chooses a random source port from a range called the ephemeral port range (temporary ports used for outgoing connections).

Usually:

Windows → 49152–65535

Linux/macOS → 32768–60999 (can vary)

Steps:

OS picks an unused random port in that range.

Assigns it to your new connection.

Uses it until the connection closes.

Frees it for reuse later.

So if you open 5 browser tabs:

Tab	Source Port	Destination Port
Tab 1	51001	443
Tab 2	51002	443
Tab 3	51003	443
Tab 4	51004	443
Tab 5	51005	443

Each tab uses a different source port → no confusion in replies.

🔢 9. How Many Ports Do We Have?

Total port numbers = 0 to 65535
Divided into ranges:

Range	Type	Use
0–1023	Well-known ports	Fixed system services (HTTP, HTTPS, DNS, etc.)
1024–49151	Registered ports	For specific apps/services
49152–65535	Ephemeral (dynamic) ports	For temporary client connections

So in theory, your device can open around 64,000 simultaneous unique connections at once — practically limited by CPU/RAM, not ports.

🧾 10. Example: Full Packet Journey Through PAT

Let’s walk through a complete example 👇

You open Google:

Source IP: 192.168.1.10
Source Port: 52000
Destination IP: 142.250.195.78
Destination Port: 443


Router applies PAT:

Source IP: 203.0.113.5
Source Port: 40001 (changed)
Destination IP: 142.250.195.78
Destination Port: 443


Google replies:

Source IP: 142.250.195.78
Source Port: 443
Destination IP: 203.0.113.5
Destination Port: 40001


Router looks in its PAT table:

203.0.113.5:40001 → 192.168.1.10:52000


It forwards the reply back to your device correctly.

🔍 11. Verification & Troubleshooting (Cisco Example)

Useful commands:

show ip nat translations     → see active translations
show ip nat statistics       → view stats (hits, misses, overload)
clear ip nat translation *   → clear all translations
debug ip nat                 → see live translation process


Common issues:

Missing ip nat inside or ip nat outside on interfaces → NAT won’t work.

Wrong ACL for NAT → packets not matched.

Port conflicts if multiple devices need same public port.

Routing problems — NAT doesn’t fix routing by itself.

🧠 12. How Port Numbers Relate to Tabs & Apps

Every tab, browser session, or app uses a unique source port.
That’s how your computer keeps connections separate.
So yes, more ports = more simultaneous connections possible.

But practically:

Your laptop can open thousands of tabs, not millions.

Limiting factor = memory, not ports.

🧩 13. Security & Real-World Notes

NAT/PAT hides internal IPs, but it’s not a security tool — it’s more of an addressing trick.

To protect networks, use firewalls with NAT.

Some protocols (like FTP, SIP, VPNs) can break under NAT because they carry IP info inside payloads. They use NAT Traversal to fix this.

🧮 14. Example Cisco Configurations

PAT (Overload):

access-list 1 permit 192.168.1.0 0.0.0.255
ip nat inside source list 1 interface GigabitEthernet0/0 overload

interface GigabitEthernet0/1
 ip address 192.168.1.1 255.255.255.0
 ip nat inside

interface GigabitEthernet0/0
 ip address 203.0.113.5 255.255.255.248
 ip nat outside


Static NAT:

ip nat inside source static 192.168.1.10 203.0.113.10


Port Forwarding Example:

ip nat inside source static tcp 192.168.1.10 80 interface GigabitEthernet0/0 8080

🧠 15. Key Takeaways (Final Revision Sheet)

✅ NAT — changes IPs (private ↔ public).
✅ PAT — changes IPs + ports, allows many devices to share one IP.
✅ Destination ports — define service type (HTTP, HTTPS, etc.).
✅ Source ports — chosen randomly by your OS (for unique sessions).
✅ PAT changes only source port — to keep sessions unique.
✅ Port range — 0–65535 (49152–65535 = ephemeral).
✅ Each connection/tab — uses a unique source port.
✅ Router’s translation table — maps public IP+port ↔ private IP+port.
✅ Ports don’t define limit of tabs directly, but they are required for separate sessions.
✅ Without port translation, NAT couldn’t handle multiple devices sharing one IP.
