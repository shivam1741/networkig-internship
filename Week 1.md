# Day 1
On Day 1 of our Netwokring Internship, we brushed networking basics with the following topics:

1. ***Definition of Networking:***
Networking is nothing but the internet that we use in daily basis, how the devices communicate to each other using internet is a networking.
2. ***Components of Networking:***
To make the internet and computer networks work smoothly, we need multiple networking devices and components such as switches, routers, hubs, and bridges etc..
   * We can these devices or components into 2 types.
  
      * ***END Devices:***   
      
         * End devices are the devices that start, receive, or end communication in a network.
         * They are the source and destination of data transmission.
     
      * ***Intermediary Devices:*** Intermediary devices are devices that connect end devices and ensure the smooth flow of data across the network.
     
      
                            
3. ***Topologies:*** Topology is the arrangement or layout of different devices (like computers, routers, switches) in a network and how they are connected to each other.  
    * ***Types of Different topologies:***   
         * ***Bus topology:*** All devices are connected to a single cable.
         * ***Star Topology:*** All devices connect to a central device (like a switch or hub).
         * ***Ring Topology:*** Devices are connected in a closed loop.
         * ***Mesh Topology:*** Devices are interconnected, so there are multiple paths between devices.
5.  Star, Bus, Ring, Mesh.
- Types of Network: PAN, LAN, MAN, WAN.
- Learned the basic network flow.
- Discussed on common Network challenges: Unauthorized access, Data breach, Viruses.
- Additionally, we went through some performance issues in network: Network Congestion, Conneciton Reliability and Bandwidth limitations.  
[DAY 1](https://claude.ai/public/artifacts/e92959cb-3269-4546-b97d-e5dcd0aee458)
# Day 2
On Day 2 of our Networking Internship, We learnt more about LAN, MAN and WAN.  
## Network Planning Exercise  
### Scenario: 
You are IT consultant for "EduTech Solutions" - an educational software company.

### Company Details:
- Main office: 100 employees in downtown building
- Development center: 50 employees, 5 km away
- Regional sales offices: 3 locations across the state
- Remote workers: 25 employees working from home
### Your Task: Design a network architecture plan identifying:
- What type of network for main office? (LAN/MAN/WAN)
- How to connect development center? (LAN/MAN/WAN)
- How to connect regional offices? (LAN/MAN/WAN)
- How to support remote workers? (LAN/MAN/WAN)
  
[DAY 2](https://claude.ai/public/artifacts/f4b54e55-0e65-4185-8eb1-4ecbebbdf880)  

# Day 3  
On Day 3 we learnt following things about Media Access Control (MAC) and Internet Protocol (IP) addresses.  
- Definition of Network Addresses. 
- How IP and MAC addresses are different to each other.
- Key Characteristics of Physical address(MAC)
     * Physical Address: Burned into network interface card (NIC).
     * Unique Worldwide: No two devices have the same MAC address.
     * 48-bit Address: 6 groups of 2 hexadecimal digits.
     * Layer 2(Data link): Works at Data Link Layer.
     * Non-routable: Only works within local network segment.
 - Key Characteristics of IP address
     * Logical Address: Assigned by network configuration.
     * Hierarchical: Network portion + Host portion.
     * 32-bit Address (IPv4): 4 groups of decimal numbers (0-255).
     * Layer 3(Network): Works at Network Layer.
     * Routable: Can be used across different networks.
  - How MAC and IP Addresses Work Together.
  - What is Packet and how it transmit (form source to destination).
  - We got to learn what Address Resolution Protocol (ARP) is and when it comes into play.
    
# NOTE  
## IP Addressing – Full Summary
1. What is an IP Address?
- An IP address is like a digital address for a device.
- It helps devices find and communicate with each other.

2. Types of IP Addresses


|Type      | Description|
|--------  |-------------
|Public ip |Given by ISP, used to connect to the internet|
|Private ip|Used inside local networks (home, office)| 
---------------------------------------------------------

 3. IP Classes and Ranges


|Class  | Range  | Private IP range | Use Case |
|-------|--------|------------------|----------|
| A     |1.0.0.0 – 126.255.255.255|10.0.0.0 – 10.255.255.255|Large networks (e.g., multinational corporations)|
| B     |128.0.0.0 – 191.255.255.255|172.16.0.0 – 172.31.255.255|Medium-sized networks (e.g., universities, large businesses)|
| C     |192.0.0.0 – 223.255.255.255|192.168.0.0 – 192.168.255.255|Small networks (e.g., home, small office LANs|Multicasting (e.g., streaming media, routing protocols)|
| D     |224.0.0.0 – 239.255.255.255|Not applicable|Multicasting (e.g., streaming media, routing protocols)|
| E     |240.0.0.0 – 255.255.255.255|Not applicable|Experimental, research purposes only|
---------------------------------------------------------------------------------------------------------

 4. Why Divide IPs into Classes?
- To match network sizes
- To organize IP distribution
- To simplify routing
- To reserve private IPs for internal use

 5. What Happens When You Install Wi-Fi at Home?
- Your ISP gives your router a public IP.
- Your router gives private IPs to connected devices (like 192.168.0.2, 192.168.0.3, etc.).
- Your home network is private, but it connects to the public internet through the router.

 6. Role of Towers and Routers
- Towers and routers are given public IPs by the ISP.
- They assign private IPs to devices connected to them.
- They use DHCP to assign IPs and NAT to translate private IPs to public IPs for internet access.

 7. If We Didn’t Divide IPs
- There would be conflicts, wasted IPs, and routing problems.
- The internet would be hard to manage and less secure.


 Final Summary:
- ISPs assign public IPs to routers and towers.
- Routers/towers assign private IPs to connected devices.
- IPs are divided into classes to organize, scale, and secure the internet.
             
