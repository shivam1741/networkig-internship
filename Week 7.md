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
* ***Basic Points:***
    * Developed by Cisco (works only on Cisco routers)
    * Creates one virtual gateway IP
    * One router is Active → handles traffic
    * Another router is Standby → takes over when Active fails
    * Election based on priority
    * Hello timer: 3 sec
    * Hold timer: 10 sec
    * Traffic always goes through the Active router (no load balancing)
