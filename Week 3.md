# Day 1 (Spanning Tree Protocol (STP))
## Spanning Tree Protocol (STP)

### What is STP?

Spanning Tree Protocol (STP) is a network protocol that ensures a **loop-free topology** for Ethernet networks. It was originally defined in IEEE 802.1D and is crucial for preventing broadcast storms and multiple frame copies caused by network loops.

### Purpose of STP

- **Prevent Layer 2 loops** in a switched network.
- **Ensure redundancy** by allowing backup paths without causing loops.
- **Maintain network stability** by dynamically blocking and unblocking ports.


### How STP Works

STP elects a **Root Bridge** and calculates the shortest path to it from all switches. It then blocks redundant paths to prevent loops.

### Key Steps:

1. **Root Bridge Election**: The switch with the lowest Bridge ID becomes the root.
2. **Path Cost Calculation**: Each switch calculates the cost to reach the root.
3. **Port Roles Assignment**:
   - **Root Port**: Best path to the root bridge.
   - **Designated Port**: Best path for a segment.
   - **Blocked Port**: Redundant path, blocked to prevent loops.
4. **Port States**:
   - **Blocking**
   - **Listening**
   - **Learning**
   - **Forwarding**
   - **Disabled**



### Types of STP

|Type|Description|
|----|-----------|
|STP (802.1D)|Original standard, slower convergence.|
|RSTP (802.1w) | Rapid STP, faster convergence.|
|MSTP (802.1s) | Multiple STP instances over VLANs.|
|PVST+ | Cisco proprietary, per-VLAN STP.|


### Benefits of STP

- Loop Prevention
- Redundancy Support
- Improved Network Reliability
- Automatic Topology Adjustment


### Example Scenario

Imagine three switches connected in a triangle. Without STP, frames could loop endlessly. STP blocks one of the links, creating a loop-free tree structure.

### Reference [ Day 1(Spanning Tree Protocol (STP))](https://claude.ai/public/artifacts/83161f5d-1c14-4ed0-8720-8f0c4d1c951b)

# Day 2 (Routing)

## Routing Basics

### What is Routing?

Routing is the process of selecting paths in a network along which to send data packets. It occurs at Layer 3 (Network Layer) of the OSI model and is essential for communication between different networks.


### Real-World Example   
Think of routing like using Google Maps to drive from your home to work:

* Your car = Data packet
* Roads = Network links
* Intersections = Routers
* GPS directions = Routing table
* Alternative routes = Backup paths

### Why is Routing Important?

Routing enables devices on different networks to communicate with each other. Without routing, data would be confined to a single local network.

### Key Concepts

* **Router:**
 A router is a network device that forwards data packets between computer networks. It uses routing tables and protocols to determine the best path for data.

*  **Routing Table:** A  routing table is a database in a router that stores paths to various network destinations, Or a routing table is like a GPS database - it contains directions to reach different networks.      
      * It includes:
        - ***Destination IP:*** Where the data wants to go (e.g., 192.168.1.0).
        - ***Subnet mask:*** It tells Which devices are in same network.
        - ***Next hop:*** The next router to send data to (e.g., 10.0.0.1)
        - ***Interface:*** Which port to send data out (e.g., Ethernet0)
        - ***Metric (cost):*** How "far" or "expensive" the route is. 

*  **Next Hop**
  The next hop is the next router or device a packet should go to on its way to the destination.



### Types of Routing

### 1. ***Static Routing:*** 
- Static routing means a network administrator manually types in the routes. The router doesn't learn routes automatically.
- Manually configured by an administrator.
- Simple and predictable.
- Not scalable for large networks.

### 2. ***Dynamic Routing:*** Dynamic routing means routers automatically share information with each other to learn the best paths. No manual configuration of individual routes needed!
- Routers automatically learn and update routes using routing protocols.
- More scalable and fault-tolerant.



### Common Routing Protocols

|Protocol|Type|Description|
|--------|----|-----------|
|RIP     |Distance Vector (Makes decisions based on distance (hop count))|Uses hop count as a metric. Simple but slow.|
|OSPF|Link State|Fast convergence, uses cost as a metric.|
|EIGRP|Hybrid|Cisco proprietary; combines distance vector & link state.|
|BGP|Path Vector|Used for routing between ISPs across the Internet.|


### How Routing Works (Simplified)
* ***Packet Arrives:*** Router receives data to forward
* ***Check Destination:*** Look at where data wants to go
* ***Find Best Match:*** Search routing table for best route
* ***Forward Packet:*** Send data to next hop router
* ***Repeat:*** Next router does the same process

***Note(Important):** If no route exists in the table, the data gets dropped! This is why complete routing tables are crucial for network connectivity.*



### Benefits of Routing

- Enables communication across networks
- Supports redundancy and failover
- Scales well for large networks
- Can enforce security policies



### Example Scenario

Imagine a company with two branches: one in Bangalore and one in Delhi. Each has its own local network. Routers at both locations use routing to allow employees to access resources across branches.


### Reference [Day 2(Routing)](https://claude.ai/public/artifacts/1921e117-1ea7-41d9-aefb-c5beb03b1c6b)

# Day 3(Interdomain & Intradomain Routing (RIP))
### Intradomain & Interdomain Networking:
* Intradomain & Interdomain Networking are the Types of Dynamic Routing.
* ***Intradomain (IGP):***
  Routing within a single organization or network Same administrative authority  
  Examples: RIP, OSPF, EIGRP
* ***Interdomain (EGP):***
  Routing between different organizations Different administrative authorities  
  Example: BGP
* ***Note:*** Think of it like
     * Intradomain = Roads within your city
     * Interdomain = Highways between cities
### Routing Information Protocol(RIP):
One of the oldest intradomain routing protocols
* ***Distance Vector Protocol:*** Makes decisions based on distance (hop count).
* ***Metric:*** Uses hop count only (max 15 hops, 16 = unreachable)
* ***Updates:*** Sends entire routing table every 30 seconds
* ***Algorithm:*** Bellman-Ford algorithm
* ***Simple Analogy:*** RIP is like asking for directions where people tell you "turn left, go 3 blocks" - it only cares about number of turns, not actual distance or traffic!
  ### RIP Versions:
  |Feature|RIPv1|RIPv2|
  |-------|-----|-----|
  |Classful/Classless|Classful|Classless|
  |Subnet Mask|Not sent|Sent in updates|
  |Updates|Broadcast|Multicast (224.0.0.9)|
  |Authentication|No|Yes (MD5/Plain text)|
  |VLSM Support|	No	|Yes|
* Today, RIPv2 is the standard version used in networks.
  ### How RIP Works:
  ***1. Initial State:*** Router only knows directly connected networks.  
  ***2. Share Information:*** Every 30 seconds, router broadcasts its routing table to neighbors.  
  ***3. Receive Updates:*** Router receives tables from neighbors.  
  ***4. Calculate Best Path:*** For each destination, choose path with lowest hop count.  
  ***5. Update Table:*** Add new routes or update existing ones if better path found.  
  ***6. Repeat:*** Process continues every 30 seconds.
  ### RIP Timers:
* ***Update Timer (30s):*** How often router sends its routing table to neighbors.
* ***Invalid Timer (180s):*** If no update received for 180s, route marked as invalid (metric set to 16).
*  ***Holddown Timer (180s):*** Time to wait before accepting new information about a failed route.
*  ***Flush Timer (240s):*** After this time, route is completely removed from routing table.

  ### Real World Use Case:
* ***Scenario:*** A retail company with 10-15 branch offices, each with 3-4 routers

* Why RIP?

   * Network is small (under 15 hops)
   * Simple to configure - minimal IT staff at branches
   * Low cost - works on basic routers
   * Easy troubleshooting for non-experts
   * ***Example:*** Branch office has Sales VLAN, Admin VLAN, and Warehouse VLAN. Each VLAN on different router interface. RIP automatically shares these networks with all routers in the branch.
 
  ### Reference [Day 3(Interdomain & Intradomain Routing (RIP))](https://claude.ai/public/artifacts/a28f54e1-e72b-4bdd-af38-6201ec24618a)
