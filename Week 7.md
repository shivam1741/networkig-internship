# Day 1 (Router Redundancy (HSRP, VRRP, GLBP))

## Why We Need Router Redundancy
* In any network, if the main router fails, the entire network goes down.
* So we use redundancy protocols → to provide backup routers that take over automatically.
* Three major FHRP (First Hop Redundancy Protocols):
   1. HSRP – Cisco proprietary
   2. VRRP – Open Standard
   3. GLBP – Cisco proprietary (but does load balancing)

## HSRP (Hot Standby Router Protocol)
* HSRP is a Cisco protocol that keeps your network gateway always available.
* If one router goes down, another router immediately takes over — users don’t feel anything.
### Basic Points:
   * Developed by Cisco (works only on Cisco routers)
   * Creates one virtual gateway IP
   * One router is Active → handles traffic
   * Another router is Standby → takes over when Active fails
   * Election based on priority
   * Hello timer: 3 sec
   * Hold timer: 10 sec
   * Traffic always goes through the Active router (no load balancing)
### How HSRP works
   * You configure a group of routers with the same HSRP group number
   * You assign a virtual IP (gateway for clients)
   * Routers decide who becomes Active (highest priority)
   * Standby router keeps listening
   * If Active router fails → Standby becomes Active instantly

### HSRP Diagram
  ![HSRP](https://github.com/shivam1741/networkig-internship/blob/Assets/ChatGPT%20Image%20Dec%204%2C%202025%2C%2007_59_33%20AM.png)

## VRRP (Virtual Router Redundancy Protocol)
 * VRRP is an open standard redundancy protocol.
 * It allows different vendor routers (Cisco, Juniper, HP) to work together for gateway backup.

### Basic Points
  * Open Standard (not Cisco-only)
  * Works like HSRP but standardized
  * Has Master and Backup routers
  * Master holds the virtual IP
  * Sends advertisements every 1 second
  * Faster failover than default HSRP timers

### How VRRP works
 * One router becomes Master (highest priority or owns the virtual IP)
 * Other routers remain Backup
 * All clients use one virtual IP
 * If Master fails → Backup instantly becomes Master
 * No load balancing by default

 ### VRRP Diagram
   ![VRRP](https://github.com/shivam1741/networkig-internship/blob/Assets/ChatGPT%20Image%20Dec%204%2C%202025%2C%2007_59_57%20AM.png)

## GLBP (Gateway Load Balancing Protocol)
 * GLBP is a Cisco protocol that gives you redundancy + load balancing together.
 * Unlike HSRP/VRRP, all routers can forward traffic at the same time.

### Basic Points
 * Cisco proprietary
 * Supports load balancing (unique feature)
 * One router becomes AVG (controller)
 * Other routers become AVFs (forwarders)
 * Each AVF gets a different virtual MAC address
 * Clients get distributed across routers automatically

### How GLBP works
 * You create a GLBP group and assign a virtual IP
 * One router becomes AVG (assigns MACs to others)
 * Other routers become AVFs (forward actual traffic)
 * Clients are balanced across all routers
 * If one AVF fails → AVG assigns its load to remaining AVFs

## Router Redundancy Comparison (HSRP vs VRRP vs GLBP)

| Feature | HSRP | VRRP | GLBP |
|--------|------|------|------|
| Type | Cisco proprietary | Open standard | Cisco proprietary |
| Mode | Active–Standby | Master–Backup | **Multiple Active** |
| Load Balancing |  No |  No |  Yes |
| Preemption | Off by default | On by default | On by default |
| Virtual IP | Yes | Yes | Yes |
| Virtual MAC | Cisco MAC | Standard MAC | Cisco MAC |
| Best Use | Basic redundancy | Multi-vendor | Redundancy + Load Balancing |

**HSRP →** Only one active router.  
**VRRP →** Same idea as HSRP but open standard.  
**GLBP →** All routers share traffic (load balancing).

# Day 2 (VPNs and Tunneling Concepts)
### What is a VPN?  
A VPN (Virtual Private Network) is a technology that allows you to create a secure and private connection over the normal internet. 
> Think of it like:    
> Normal internet = open road (anyone can see you)   
> VPN = private tunnel inside that road (only you can travel, nobody sees)    
***VPN keeps your:***   
* Data safe
* Identity hidden
* Traffic encrypted
* Location disguised 

 

### Why do we need a VPN? 
Because the internet is not private by default.    
When you browse normally, these can see what you're doing: 
* ISP (Internet Service Provider)
* Public Wi-Fi owners
* Hackers on the same network
* Data thieves
* Advertisers
* VPN fixes this by hiding and encrypting everything. 

 

  

### How does a VPN actually work?  
* Step 1 — You connect to the internet 
Wi-Fi / Mobile data / Public Wi-Fi 
* Step 2 — You connect to a VPN Server 
Using VPN app (Nord, Cisco, FortiClient, Zscaler etc.) 
* Step 3 — VPN creates an Encrypted Tunnel 
This tunnel protects your data. 
* Step 4 — Your traffic goes to the internet through the VPN server 
So websites see the VPN server, not you. 
* Step 5 — ISP or Hacker cannot read your data 
They only see encrypted junk. 

 

### Important VPN Concepts  

 * ***Encryption***   
 Encryption scrambles your data so even if someone catches it, they cannot read it. 
 It uses keys like:   
    * AES-256
    * SSL/TLS
    * IPSec 

 * ***Tunneling***     
 This is the method used to carry your encrypted data safely. 
 Protocols used: 
    * IPSec
    * OpenVPN
    * WireGuard
    * L2TP
    * SSTP
 * ***Authentication***    
 VPN checks your identity using: 
    * Username
    * Password
    * OTP
    * Certificates
    * MFA (Multi-Factor Authentication) 

 * ***IP Address Change***    
 VPN hides your real IP and gives you a new one. 

### Types of VPN  

1. ***Remote Access VPN***
    * Allows individual users to connect to a private network from remote locations.
    * Use Case: Remote employees accessing company resources
    * Example: Employee working from home connecting to office network 

 

2. ***Site-to-Site VPN*** 
    * Connects entire networks to each other, typically used to link branch offices.
    * Use Case: Connecting multiple office locations
    * Example: Headquarters connected to regional offices 

 

3. ***Client-to-Site VPN (SSL VPN)*** 
    * Individual client connects to a specific network or site.
    * Use Case: Secure access to corporate applications
    * Example: Contractor accessing project management system 

 

4. ***SSL/TLS VPN***
    * Browser-based VPN using SSL/TLS protocols for encryption.
    * Use Case: Web-based applications without client software
    * Example: Accessing webmail through secure browser connection 

 (***What Is SSL Inspection?***    
 SSL Inspection means the firewall decrypts encrypted traffic, checks it for threats, and then re-encrypts it before sending it to the destination.) 

 
### VPN Modes: 

 * ***Full Tunnel***
     * All your traffic goes through VPN 
     * Maximum security 
     * Slower internet sometimes 

* ***Split Tunnel***
    * Only specific traffic goes through VPN
    * Faster internet
    * Used mostly in corporate 

 

 

### What VPN Hides? 

 * Your browsing data
 * Your IP address
 * Your location
 * Your online activities
 * What websites you're opening 

### What VPN Cannot Hide? 

 * VPN cannot hide things from:
 * The VPN provider itself
 * The website you visit (if you log in)
 * Government (if VPN company is forced to share data)
 * But ISP cannot see your activities. 

