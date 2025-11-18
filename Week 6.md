# Day 1(ACL) 
## ACL (Access Control List)

* ACL (Access Control List) is like a security guard in networking.
* It controls which packets (data) are allowed in or out of a network or device (like a router).
* In simple words:
> ACL decides who can enter and who can’t.
* ***Real-life Examples:***
     - Think of your router as a building gate.
     - People (packets) want to enter.
     -  The security guard (ACL) checks a list:
         > If your name (IP address, port, or protocol) is allowed --> you enter.   
         > If not --> you’re blocked.   
         
  So, ACL is that list of rules used by routers or firewalls to decide what traffic can pass.

* In the following image we can see that how ACL works actually.
 
 ![ACL](https://github.com/shivam1741/networkig-internship/blob/Assets/ACL.jpg)


### What ACL Can Filter:
* Source IP address (where data is coming from)
* Destination IP address (where data is going)
* Protocol (like TCP, UDP, ICMP)
* Port number (like HTTP = 80, HTTPS = 443)

### Why We Need ACL
|Reason|Explanation|
|------|-----------|
|Security|Blocks unwanted or harmful traffic (like hackers).|
|Traffic Control|Limits what kind of data can pass (e.g., only allow web browsing, block FTP).|
|Network Performance|Reduces unnecessary traffic to improve speed.|
|Monitoring|Helps track or log who’s accessing the network.|

### Types of ACL
|Type |Description|	Example|
|-----|------------|--------|
|Standard ACL|	Filters only based on Source IP address|Allow only specific IPs to access network.|
|Extended ACL |Filters based on Source + Destination + Protocol + Port| Allow only HTTP traffic from specific users.|
|Named ACL|ACLs with a name instead of a number, easier to manage|ip access-list extended WEB_FILTER|
|Numbered ACL|Identified by a number (1–99 = Standard, 100–199 = Extended)|access-list 101 permit tcp any any eq 80|


### Where ACL is Used
* Routers → to control which traffic enters or leaves the network.
* Firewalls → to block or allow traffic based on rules.
* Switches → to manage traffic between VLANs.


# Day 2(Firewall)

## Firewall
A Firewall is a security device/software that monitors, filters, and controls incoming and outgoing network traffic based on security rules.   
Or   
A firewall is a security gatekeeper that allows safe traffic and blocks harmful traffic based on pre-defined security rules.
> Think of it like a security guard standing at the network gate.

### Why Do We Need a Firewall?
A firewall protects your network from:
> Hackers    
> Unauthorized access    
> Malware    
> Suspicious traffic    
> Unwanted websites   
> External attacks


It ensures that only safe traffic enters your network.

### How Firewall Works
Every packet of data entering or leaving your network goes through the firewall.   
The firewall checks:
> Source IP    
> Destination IP    
> Port number    
> Protocol   
> Traffic type 


Then it decides:   
> ALLOW    
> BLOCK     
> LOG    
> INSPECT  

### Types of Firewall

* ***Packet Filtering Firewall***
   * Oldest type
   * Checks only headers (IP, port)
   * Fast but not very secure  

* ***Stateful Inspection Firewall***
   * Tracks active connections
   * More secure than packet filter

* ***Proxy Firewall (Application Layer Firewall)***
   * Works at Layer 7
   * Filters HTTP, DNS, FTP, etc.
   * Very secure but slower

* ***NGFW – Next Generation Firewall***   
Most modern firewalls are NGFW with features:
   * Deep Packet Inspection
   * IPS/IDS
   * URL filtering
   * Application Control
   * Malware detection
   * SSL inspection

* ***Software Firewall***
   * Installed on PC (Windows Firewall)

* ***Hardware Firewall***
   * Dedicated appliance (Palo Alto / FortiGate / Cisco ASA)
 

### Firewall Limitations
* Cannot detect all attacks (IPS required)
* Cannot stop insider threats
* Cannot block encrypted threats unless SSL inspection is ON
* Needs proper configuration     
* ***What Is SSL Inspection?***   
SSL Inspection means the firewall decrypts encrypted traffic, checks it for threats, and then re-encrypts it before sending it to the destination.


## How Firewall is different from ACL

***ACL***

* Basic filtering (IP + Port only)
* Can only allow or deny
* No deep inspection, no security
* Works on Layer 3 & 4
* ACL can be added inside routers and switches

***Firewall***

* Advanced security system
* Scans traffic, apps, malware, threats
* Can decrypt HTTPS
* Works up to Layer 7
* Firewall requires a separate dedicated device/tool
* In short
> ACL = Basic IP/Port filter inside router/switch    
> Firewall = Separate security device for full protection
