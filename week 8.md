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
ping sends ICMP (Internet Control Message Protocol) Echo Request packets to the target host and waits for Echo Reply 
packets.

### When we use ping

| **Use Case**                    | **Why We Use Ping**                    | **Example Command**    | **What You Understand From Result**                    |
| ------------------------------- | -------------------------------------- | ---------------------- | ------------------------------------------------------ |
| **Check basic connectivity**    | To see if a device/server is reachable | `ping 192.168.1.1`     | Reply = device UP; No reply = device DOWN/blocked      |
| **Check internet availability** | To test if internet works              | `ping 8.8.8.8`         | If reply → internet OK; If no reply → ISP/router issue |
| **Check DNS problem**           | To compare IP vs domain                | `ping google.com`      | IP works but domain fails → DNS issue                  |
| **Check latency (ms)**          | To test speed/delay                    | `ping 8.8.8.8`         | Higher ms = slow; Lower ms = fast                      |
| **Check packet loss**           | To find unstable network               | `ping -n 20 8.8.8.8`   | Shows % of lost packets                                |
| **Check LAN connection**        | To test gateway/local network          | `ping 192.168.0.1`     | If gateway unreachable → LAN issue                     |
| **Continuous monitoring**       | To check stability over time           | `ping -t 8.8.8.8`      | Shows continuous ping until stopped                    |
| **Test with large packet size** | To check MTU issues                    | `ping -l 1500 8.8.8.8` | If fails, fragmentation/MTU problem                    |
| **Check specific timeout**      | To see how quick reply comes           | `ping -w 500 8.8.8.8`  | Fails if reply takes more than 500 ms                  |


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

 ### Useful Tracert Options
 1. ***Resolve hostnames***
     ``` tracert -d google.com ```
    * It is faster.
    * It shows IP only not DNS lookup
    
 2. ***Increase max hops***
     ``` tracert -h 50 google.com ```
    * It increase hops.

  3. ***Set timeout***
     ``` tracert -w 500 google.com ```
     * Normally, tracert waits 4000 ms (4 seconds).
     * That is too long, especially if many hops are slow or non-responsive.
     * That's why we can use this command to set a timeout.


  ### When to use Tracert
  
  | Issue               | Why Use Tracert                  |
| ------------------- | -------------------------------- |
| Slow internet       | Find which hop has high latency  |
| Website not opening | Check path break                 |
| Packet drop         | Identify failing router          |
| Routing issue       | See actual path vs expected path |





## telnet - Remote Connection Testing
* ```telnet``` is a protocol and command-line tool used to establish a connection to a remote host. While it was originally used for remote system administration, today it's primarily used for testing connectivity to specific ports.
* It checks application-level connectivity, not just IP.
* ```telnet``` transmits data in plain text, making it insecure for actual remote administration.


### How Telnet Works
* Telnet tries to create a TCP connection to a specific port.
* If connection opens → port is reachable
* If connection fails → port is blocked, service is down, or server unreachable
 > Ping only checks IP.    
 > Telnet checks both IP + Port.
