# Day 1 (OSI Model)

## OSI Model:
On the 1st day of the 2nd week I got to learn about **OSI Modal** and its layers with function of each.
- **To remember its layers into sequance we learnt a trick that is "All People Seem To Need Data Processing".**
    * All- Application Layer(7)
    * People- Presentation Layer(6)
    * Seem- Session Layer(5)
    * To- Transport layer(4)
    * Need- Network Layer(3)
    * Data- Data Link Layer(2)
    * Processing- Physical Layer(1)
 - In the following image we will understand it well.
  ![OSI Model](https://github.com/shivam1741/networkig-internship/blob/Assets/OSI%20modal.png)

 - Let's study actual functions of every layers:
    * **Application Layer**

      - It is the layer that is responsible for giving user friendlly interface for User interaction.
      - It uses application level protocols such as
      
       > HTTP/HTTPS – for web browsing    
       > FTP – for file transfers    
       > SMTP/POP3/IMAP – for email   
       > DNS – for domain name resolution   
       > Telnet/SSH – for remote access
     * **Presentation Layer**

       - The presentation layer is responsible for translating data formats, encrypting and decrypting data for security, and compressing data to reduce size during transmission.
         
     * **Session Layer:**
       - The session layer is responsible for establishing, managing, and terminating communication sessions between applications. It controls dialog between systems, ensuring data exchange is organized and synchronized.
      
    * **Transport Layer:**
       - The transport layer is responsible for reliable data transfer between devices. It ensures error-free delivery, proper sequencing, and flow control, using protocols like TCP and UDP.

    * **Network Layer:**
      - The network layer is responsible for routing data between devices across different networks. It assigns logical addresses (like IP) and determines the best path for data delivery.

    * **Data Link Layer:**
       - The data link layer is responsible for reliable data transfer between two directly connected nodes. It handles error detection, correction, and framing of data for transmission over the physical layer.

     * **Physical Layer:**
       - The physical layer is responsible for transmitting raw bits over a physical medium such as cables or wireless signals. It defines hardware specifications, signal types, and data rates for communication.                 
     
   
  
### Example Where OSI Model is followed: 
How OSI Modal is used when we access any web page.
- ***Application Layer-*** Browser works here, It give you the interface to request a web page.
- ***Presentation Layer-*** Here Data is encrypted so no one can read it, and compressed for faster tansfer.
- ***Session Layer-*** It create secure session b/w user and server.
- ***Transport Layer-*** Here we use UDP And TCP protocol, but in this case TCP protocol is used ensuring that no data is lost while transferring.
- ***Network Layer-*** The DNS will change into IP and Find best way to transfer data fast.
- ***Data link Layer-*** Here network interface card (NIC) puts the IP and source's Mac and router's Mac to every frames
- ***Physical layer-*** Data is sent as electrical signals(Ethernet cable) or radio waves(Wi-fi/Cellular networks(3G, 4G, 5G)).




# Day 2 (TCP/IP Model)  
## TCP/IP Model

The TCP/IP model (Internet Protocol Suite) is a conceptual framework used to describe how data is transmitted over a network. It consists of 4 layers, each with specific responsibilities.

  In the following image we will get some idea how TCP/IP actually works
![TCP/IP](https://github.com/shivam1741/networkig-internship/blob/Assets/https___dev-to-uploads.s3.amazonaws.com_uploads_articles_602dnkhd6i3rpnk51j0r.webp)



### 1. Application Layer
- Purpose: Provides services directly to user applications.
- Examples: `HTTP`, `FTP`, `SMTP`, `DNS`
- Functions:
  - Data formatting
  - Encryption
  - Session management



### 2. Transport Layer
- Purpose: Ensures reliable data transfer between devices.
- Protocols:
  - `TCP` (Transmission Control Protocol): Reliable, connection-oriented
  - `UDP` (User Datagram Protocol): Fast, connectionless
- Functions:
  - Error detection and correction
  - Flow control
  - Segmentation and reassembly



### 3. Internet Layer
- Purpose: Handles logical addressing and routing.
- Main Protocol: `IP` (Internet Protocol)
- Functions:
  - Routing packets across networks
  - IP addressing
  - Fragmentation and reassembly



### 4. Network Access Layer (Link Layer)
- Purpose: Deals with physical transmission of data.
- Includes: `Ethernet`, `Wi-Fi`, `ARP`
- Functions:
  - Framing
  - MAC addressing
  - Physical transmission over cables or wireless



### Comparison with OSI Model

![TCP/IP Model](https://github.com/shivam1741/networkig-internship/blob/Assets/OSI-to-TCPIP-Model.png)

### Key Points
- TCP/IP is practical and widely used in real-world networking.
- It’s the foundation of the Internet.
- Each layer serves a specific role in data transmission.

# Day 3 (Switches)
## Switches

- A network switch is a device that connects multiple devices (like computers, printers, servers) within a Local Area Network (LAN) and allows them to communicate with each other efficiently.
- Think of it like a traffic controller at a busy intersection — it makes sure data goes to the right destination without crashing into other data.

### Basic Concepts 

- Devices (like PCs, printers) connect to the switch using Ethernet cables.
- The switch uses MAC addresses (unique IDs for each device) to know where to send data.
- It works at Layer 2 of the OSI model (Data Link Layer), but some advanced switches also work at Layer 3 (Network Layer).

### What Is a Layer 2 Switch?
A Layer 2 switch is a network device that operates at the Data Link Layer (Layer 2) of the OSI model. It uses MAC addresses to forward data between devices within the same local network (LAN).

 **Basic Functions**

- ***MAC Address Learning:*** It learns the MAC addresses of devices connected to each port.
- ***Forwarding Frames:*** It forwards Ethernet frames only to the port where the destination device is connected.
- ***Filtering Traffic:*** Prevents unnecessary traffic from reaching devices that don’t need it.
- ***Collision Domain Isolation:*** Each port is its own collision domain, improving performance.

## What Is a Layer 3 Switch?
A Layer 3 switch is a network switch that can perform routing functions — just like a router — in addition to switching. It operates at Layer 3 (Network Layer) of the OSI model.
So, while a Layer 2 switch forwards data based on MAC addresses, a Layer 3 switch forwards data based on IP addresses.

### Layer 2 vs Layer 3 Switches

|Feature  |Layer 2 Switch |Layer 3 Switch|
|---------|---------------|--------------|
|Works at |Data Link Layer|Network Layer|
|Forwards data using|MAC Addresses|IP addresses|
|Can route between VLANs|No|Yes|
|Supports static/dynamic routing|No|Yes|
|Ideal for|Simple LANs|Complex networks with multiple subnets and VLAN|
|Inter-VLAN Routing|❌ Requires external router|✅ Built-in routing between VLANs|
|Primary Function|Switching based on MAC addresses|Switching + Routing based on IP addresses|
|Default Gateway Functionality|❌ No|✅ Can act as default gateway|





## Subnetting and Subnet Mask:  
* **What is Subnetting?**     
Subnetting is the process of dividing a larger IP network into smaller, more manageable subnetworks (subnets). It helps improve network performance, security, and IP address management.

* **IP Address Structure**    
An IP address has 32 bits, split into:
      
  * Network portion: Identifies the network.
  * Host portion: Identifies devices within that network.

* **Subnet Mask**  
Defines how many bits are used for the network.  
Example:    

   * /24 → 24 bits for network, 8 bits for host
   * /26 → 26 bits for network, 6 bits for host


*  **Borrowing Bits**    
To create more subnets, you borrow bits from the host portion.    


 |Bits Borrowed|New Subnet Mask|Subnets Created|Hosts per Subnet|
 |-------------|---------------|---------------|----------------|
 |0            |/24            |1              | 254            |
 |1            |/25            |2              | 126            |
 |2            |/26            |3              | 62             |
 |3            |/27            |4              | 30             |
 |4            |/28            |5              | 14             |  
 
 
* **Binary Breakdown Example (/26)**    

    * Original network: 192.168.1.0/24
    * Borrow 2 bits from host → /26 → 4 subnets:   
    
    |Subnet|Binary Start of Last Octet|Decimal Range|
    |------|--------------------------|-------------|
    |1|00xxxxxx|192.168.1.0 - 192.168.1.63|
    |2|01xxxxxx|192.168.1.64 - 192.168.1.127|
    |3|10xxxxxx|192.168.1.128 - 192.168.1.191|
    |4|11xxxxxx|192.168.1.192 - 192.168.1.255|

  
     * xx... represents host bits.
     * The first two bits (00, 01, 10, 11) define the subnet.


* **Key Takeaways**    

    * Without borrowing bits, you get 1 big subnet with many hosts.
    * With borrowed bits, you get multiple smaller subnets with fewer hosts.
    * IP addresses look the same in decimal, but their binary form reveals subnet boundaries.
    * nSubnetting is essential for efficient IP usage, network segmentation, and security.


# Day 4 (VLAN)
## VLAN (Virtual Local Area Network)

### Why Do We Need VLANs?

Imagine a large office network with hundreds of devices computers, printers, IP phones all connected to switches. Without VLANs:

- Every device is part of the same broadcast domain.
- Broadcast traffic (like ARP requests) reaches every device, causing:
  - Network congestion
  - Security risks
  - Scalability issues

### VLANs solve this by:
- Logically segmenting the network.
- Reducing unnecessary traffic.
- Improving security and manageability.


### What Is a VLAN?

A VLAN (Virtual Local Area Network) is a way to group devices logically, even if they’re connected to the same physical switch.

- Devices in the same VLAN can communicate directly.
- Devices in different VLANs need a router or Layer 3 switch to talk to each other.

### Think of it like this:
Imagine an office building with different departments:

- VLAN 10 → HR  
- VLAN 20 → Finance  
- VLAN 30 → Engineering  

Even though all computers are plugged into the same switch, VLANs virtually separate them.


### Benefits of VLANs

- Improved Security: Isolate sensitive departments.
- Reduced Broadcasts: Less noise, better performance.
- Better Management: Easier to monitor and troubleshoot.
- Flexibility: Group devices logically, not just physically.

## Reference 
* [DAY 1 (OSI Model)](https://claude.ai/public/artifacts/e43d6790-fe29-45e8-887d-6f24978d1bc2?fullscreen=true)
* [Day 2 (TCP/IP Model)](https://claude.ai/public/artifacts/a1c59732-03c8-4268-bf63-c8a6b20e8c3c?fullscreen=true)

