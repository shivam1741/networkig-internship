# Day 1
On Day 1 of our Netwokring Internship, we brushed networking basics with the following topics:

1. ***Definition of Networking:***
Networking is nothing but the internet that we use in daily basis, how the devices communicate to each other using internet is a networking.
2. ***Components of Networking:***
To make the internet and computer networks work smoothly, we need multiple networking devices and components such as switches, routers, hubs, and bridges etc..
   * We can divide these devices or components into 2 types.
  
      * ***END Devices:***   
      
         * End devices are the devices that start, receive, or end communication in a network.
         * They are the source and destination of data transmission.
     
      * ***Intermediary Devices:*** Intermediary devices are devices that connect end devices and ensure the smooth flow of data across the network.
      * In the following image we can clearly see that what are ***END Devices*** and ***Intermediary Devices***.
      ![Devices](https://github.com/shivam1741/networkig-internship/blob/Assets/NodeDevices.png)
     
      
                            
3. ***Topologies:*** Topology is the arrangement or layout of different devices (like computers, routers, switches) in a network and how they are connected to each other.  
    * ***Types of Different topologies:***   
         * ***Bus topology:*** All devices are connected to a single cable.
         
         ![Bus Topology](https://github.com/shivam1741/networkig-internship/blob/Assets/A-bus-network-topology.png)
         
         * ***Star Topology:*** All devices connect to a central device (like a switch or hub).
         
         ![Star topology](https://github.com/shivam1741/networkig-internship/blob/Assets/The-star-network-topology.png)
         
         * ***Ring Topology:*** Devices are connected in a closed loop.
         
         ![Ring Topology](https://github.com/shivam1741/networkig-internship/blob/Assets/The-ring-network-topology.png)
         
         * ***Mesh Topology:*** Devices are interconnected, so there are multiple paths between devices.
         
         ![Mesh Topology](https://github.com/shivam1741/networkig-internship/blob/Assets/The-mesh-network-topology-the-full-mesh-and-partial-mesh.png)
         
  4. ***Network:*** A network is when two or more devices (like computers, phones, printers) are connected together so they can share data, files, or resources.
      * ***Types of Network:***   
           * ***PAN(Personal Area Network):*** Small network around one person, like Bluetooth devices.
           * ***LAN(Local Area Network):*** Network in a small area like home, office, or school.
           * ***MAN(Metropolitan Area Network):*** Network covering a whole city.
           * ***WAN(Wide Area Network):*** Network covering large areas, like countries or the internet.  
# Day 2
On Day 2 of our Networking Internship, We learnt more about LAN, MAN and WAN.
### LAN(Local Area Network):
* A network within a small area like a home, office, or school.
* Covers a few hundred meters or one building.
* Very high speed (up to 1 Gbps or more).
* Used to share files, printers, or internet between nearby computers.
* *Example:* Computers connected in your college lab. 

![LAN Diagram](https://github.com/shivam1741/networkig-internship/blob/Assets/LAN-Diagram.jpg)

### PAN(Personal Area Network): 
* A small network created around one person.
* Covers a range of about 10 meters.
* Used to connect personal devices like a phone, laptop, smartwatch, or Bluetooth headset.
* Doesn’t require heavy equipment — can be wireless or wired (like USB).
* *Example:* Your mobile connected to your earbuds or smartwatch.

![PAN](https://github.com/shivam1741/networkig-internship/blob/Assets/PAN.png)

### WAN(Wide Area Network):
* A network that connects devices or LANs over large geographical areas.
* Covers states, countries, or even the whole world.
* Uses public or private transmission lines (like satellites, fiber optics).
* Lower speed compared to LAN but covers long distances.
* *Example:* The Internet is the biggest WAN.

 ![WAN](https://github.com/shivam1741/networkig-internship/blob/Assets/WAN.jpg)
  
## Network Planning Exercise  
### Scenario: 
You are IT consultant for "EduTech Solutions" - an educational software company.

### Company Details:
> Main office: 100 employees in downtown building.   
> Development center: 50 employees, 5 km away.   
> Regional sales offices: 3 locations across the state.  
> Remote workers: 25 employees working from home.
### Tasks: Design a network architecture plan identifying:
- What type of network for main office? (LAN/MAN/WAN) --> ***LAN***
-  How to connect development center? (LAN/MAN/WAN) --> ***LAN***
- How to connect regional offices? (LAN/MAN/WAN) --> ***WAN***
- How to support remote workers? (LAN/MAN/WAN) --> ***WAN***


# Day 3  
On Day 3 we learnt following things about Media Access Control (MAC) and Internet Protocol (IP) addresses.  
## IP(Internet Protocol) Address:
* An IP address (Internet Protocol address) is a unique number given to every device connected to a network so that it can send and receive data.
* It’s just like a home address, but for devices on the internet or a local network — it helps identify where data should go and where it came from.
* ***Main Purpose:***
> *Identification* – tells who the device is.   
> *Location* – tells where the device is in the network.   
> *Communication* – helps devices talk to each other.

### ***Types of IP Addresses:***
* IPv4 (Internet Protocol version 4):
> 32-bit address (written like 192.168.1.1).   
> Has about 4.3 billion possible addresses.  
> *Example:* 172.16.0.1   
> Used widely even today.

* IPv6 (Internet Protocol version 6):
> 128-bit address (written with hexadecimal numbers).  
> Much larger address space (can handle billions of devices).  
> *Example:* 2001:0db8:85a3:0000:0000:8a2e:0370:7334

## MAC (Media Access Control) Address:
* MAC Address is a unique physical address given to every network device (like your laptop, router, or phone’s network card).
* It is burned into the hardware (Network Interface Card) by the manufacturer — that’s why it’s also called a hardware address or physical address.
* It is permanent and unique for each one.
* *Length:* 48 bits (6 bytes)
* *Written In:* Hexadecimal format
* *Example:* 00:1A:2B:3C:4D:5E

## How MAC and IP are different to each others:
| **Feature** | **MAC Address** | **IP Address** |
|-------------|----------------|----------------|
| **Layer**     | Works at Data Link Layer (Layer 2)| Works at Network Layer (Layer 3) |
| **Purpose**   | Identifies a specific device on a network | Identifies a device’s location in a network |
| **Type of Address**| Physical address (burned into hardware)| Logical address (assigned by network or manually) |
| **Uniqueness** | Unique worldwide for every device| Can change depending on the network |
| **Format**     | 48-bit (e.g., 00:1A:2B:3C:4D:5E)| 32-bit (IPv4, e.g., 192.168.1.5) or 128-bit (IPv6) |
| **Changeability**| Permanent (but can be spoofed)| Dynamic (changes when connected to different networks) |
| **Used For**  | Communication within a local network (LAN)| Communication across networks (WAN, Internet) |
| **Visibility** | Seen only inside the local network| Seen across the Internet |

### ARP (Address Resolution Protocol):
* ARP (Address Resolution Protocol) is a protocol used to find the MAC address of a device when we already know its IP address.
* It helps devices in the same local network talk to each other.
* To understand it well let's take an ***Example:***   

   Suppose there are two PCs in the same LAN:
          > PC1 → IP = 192.168.1.10, MAC = AA:AA:AA:AA:AA:AA   
          > PC2 → IP = 192.168.1.20, MAC = BB:BB:BB:BB:BB:BB   
 
    Now PC1 wants to send data to PC2.   
    * **Step 1:PC1 checks ARP table**   
    PC1 checks its ARP cache/table to see if it already knows PC2’s MAC address.
    * **Step 2: If not found → send ARP Request**   
    It broadcasts a message to everyone.
         > Who has IP 192.168.1.20? Tell 192.168.1.10.
         > This goes to all devices in that LAN (broadcast)
     * **Step 3: PC2 replies with ARP Reply**   
     PC2 sees it’s being asked and sends a unicast reply.
         > 192.168.1.20 is at BB:BB:BB:BB:BB:BB.
     * **Step 4: PC1 updates ARP table**   
     PC1 saves this mapping in its ARP table:
         > 192.168.1.20 → BB:BB:BB:BB:BB:BB.
     * **Step 5: Communication starts**   
     Now PC1 can send frames directly to PC2’s MAC.
     
  #### When ARP doesn’t work
   * ARP works only within the same LAN (Layer 2).
   *  If the destination is in another network, the sender sends the packet to the default gateway’s MAC, not the final device’s MAC. **(That’s where routers come into play.)**    
  
  
     

### IP Addressing(Public and Private IPs)
1. What is an IP Address?
- An IP address is like a digital address for a device.
- It helps devices find and communicate with each other.

2. Types of IP Addresses


|Type      | Description|
|--------  |-------------
|Public ip |Given by ISP, used to connect to the internet|
|Private ip|Used inside local networks (home, office)| 


 3. IP Classes and Ranges


|Class  | Range  | Private IP range | Use Case |
|-------|--------|------------------|----------|
| A     |1.0.0.0 – 126.255.255.255|10.0.0.0 – 10.255.255.255|Large networks (e.g., multinational corporations)|
| B     |128.0.0.0 – 191.255.255.255|172.16.0.0 – 172.31.255.255|Medium-sized networks (e.g., universities, large businesses)|
| C     |192.0.0.0 – 223.255.255.255|192.168.0.0 – 192.168.255.255|Small networks (e.g., home, small office LANs|Multicasting (e.g., streaming media, routing protocols)|
| D     |224.0.0.0 – 239.255.255.255|Not applicable|Multicasting (e.g., streaming media, routing protocols)|
| E     |240.0.0.0 – 255.255.255.255|Not applicable|Experimental, research purposes only|

> The class of IP is chosen based on how many devices or users need to be connected — not the type of device like router or tower.

 
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




# References
* [DAY 1.](https://claude.ai/public/artifacts/e92959cb-3269-4546-b97d-e5dcd0aee458)
* [DAY 2.](https://claude.ai/public/artifacts/f4b54e55-0e65-4185-8eb1-4ecbebbdf880)
* [Day 3.](https://claude.ai/public/artifacts/9933647d-a377-4e9e-9b69-e1e4030a2a55)
             
