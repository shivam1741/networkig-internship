# Day 1(ACL) 
## ACL (Access Control List):
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

  ![ACL]()


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


