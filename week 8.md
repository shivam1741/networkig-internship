# Network Troubleshooting Tools

## Ping

* It is a command that is used for Checks connectivity between two devices.
 ```
 ping google.com
 ping 8.8.8.8
 ```

![ping](https://github.com/shivam1741/networkig-internship/blob/Assets/Screenshot%202025-12-05%20100340.png)

* In the image we can see clearly 4 packets has been sent successfully to a sever or device whose ip is 8.8.8.8.
* In the place of IP we can use DNS name (like google.com , cisco.com) too.

### How it works
ping sends ICMP (Internet Control Message Protocol) Echo Request packets to the target host and waits for Echo Reply packets.

### Ping Visual Flow
![ping](https://github.com/shivam1741/networkig-internship/blob/Assets/Screenshot%202025-12-06%20071600.png)

## traceroute - Tracing Network Path

``` tracert ``` (Windows) or ``` traceroute ``` (Linux/Cisco) is a network troubleshooting command that shows the exact path your packet takes from your device to a destination (like google.com).   
It tells you:
* Which routers/hops your packet passes through
* How many hops it takes
* Where the delay is happening
* Where the packet is getting dropped

### How tracert works internally

* It uses ICMP Echo Requests with increasing TTL (Time To Live):
* Sends packet with TTL = 1 → first router replies “time exceeded”
* Sends packet with TTL = 2 → second router replies
* Continues increasing TTL…   
This way, it discovers each hop one by one.

### Basic Command

``` tracert google.com ```

![output](https://github.com/shivam1741/networkig-internship/blob/Assets/Screenshot%202025-12-06%20074514.png)
 ***How to understand the image***   
 * Hop 2 timed out → could be:
 * Router blocking ICMP
 * Router overloaded
 * Higher ms → indicates latency
 * Stars (*) means → no ICMP reply
