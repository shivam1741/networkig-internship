# Day 1 (OSI Model)
On the 1st day of the 2nd week I got to learn about OSI Modal and its layers with function of each.
- **To remember its layers into sequance we learnt a trick that is "All People Seem To Need Data Processing".**
    * All- Application Layer(7)
    * People- Presentation Layer(6)
    * Seem- Session Layer(5)
    * To- Transport layer(4)
    * Need- Network Layer(3)
    * Data- Data Link Layer(2)
    * Processing- Physical Layer(1)
 
-  **Sender to Receiver:**
    * **Application Layer**

      - It is the layer that is responsible for giving user friendlly interface for User interaction.
      - It uses application level protocols such as

             HTTP/HTTPS – for web browsing
             FTP – for file transfers
            SMTP/POP3/IMAP – for email
            DNS – for domain name resolution
            Telnet/SSH – for remote access
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
     
   
  
## Example Where OSI Model is followed: 
How OSI Modal is used when we access any web page.
- Application Layer- Browser works here, It give you the interface to request a web page.
- Presentation Layer- Here Data is encrypted so no one can read it, and compressed for faster tansfer.
- Session Layer- It create secure session b/w user and server.
- Transport Layer- Here we use UDP And TCP protocol, but in this case TCP protocol is used ensuring that no data is lost while transferring.
- Network Layer- The DNS will change into IP and Find best way to transfer data fast.
- Data link Layer- Here network interface card (NIC) puts the IP and source's Mac and router's Mac to every frames
- Physical layer- Data is sent as electrical signals(Ethernet cable) or radio waves(Wi-fi/Cellular networks(3G, 4G, 5G)).


### Reference [DAY 1](https://claude.ai/public/artifacts/e43d6790-fe29-45e8-887d-6f24978d1bc2?fullscreen=true)


# Day 2 (TCP/IP Model)





# Day 3 (Switches)

- A network switch is a device that connects multiple devices (like computers, printers, servers) within a Local Area Network (LAN) and allows them to communicate with each other efficiently.
- Think of it like a traffic controller at a busy intersection — it makes sure data goes to the right destination without crashing into other data.

### Basic Concepts 

- Devices (like PCs, printers) connect to the switch using Ethernet cables.
- The switch uses MAC addresses (unique IDs for each device) to know where to send data.
- It works at Layer 2 of the OSI model (Data Link Layer), but some advanced switches also work at Layer 3 (Network Layer).

