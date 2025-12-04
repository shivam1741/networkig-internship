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
