# Day 1(Spanning Tree Protocol (STP))
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

# Day 2(Routing)

## Routing Basics

### What is Routing?

Routing is the process of selecting paths in a network along which to send data packets. It occurs at Layer 3 (Network Layer) of the OSI model and is essential for communication between different networks.


### Why is Routing Important?

Routing enables devices on different networks to communicate with each other. Without routing, data would be confined to a single local network.

### Key Concepts

* **Router:**
 A router is a network device that forwards data packets between computer networks. It uses routing tables and protocols to determine the best path for data.

*  **Routing Table:**
  A  routing table is a database in a router that stores paths to various network destinations. It includes:
    - Destination IP
    - Subnet mask
    - Next hop
    - Interface
    - Metric (cost)

*  **Next Hop**
  The next hop is the next router or device a packet should go to on its way to the destination.



### Types of Routing

### 1. Static Routing
- Manually configured by an administrator.
- Simple and predictable.
- Not scalable for large networks.

### 2. Dynamic Routing
- Routers automatically learn and update routes using routing protocols.
- More scalable and fault-tolerant.



### Common Routing Protocols

|Protocol|Type|Description|
|--------|----|-----------|
|RIP     |Distance Vector|Uses hop count as a metric. Simple but slow.|
|OSPF|Link State|Fast convergence, uses cost as a metric.|
|EIGRP|Hybrid|Cisco proprietary; combines distance vector & link state.|
|BGP|Path Vector|Used for routing between ISPs across the Internet.|


### How Routing Works (Simplified)

1. A device sends a packet to an IP outside its local network.
2. The router checks its routing table.
3. It forwards the packet to the next hop.
4. This continues until the packet reaches its destination.



### Benefits of Routing

- Enables communication across networks
- Supports redundancy and failover
- Scales well for large networks
- Can enforce security policies



### Example Scenario

Imagine a company with two branches: one in Bangalore and one in Delhi. Each has its own local network. Routers at both locations use routing to allow employees to access resources across branches.


### Reference [Day 2(Routing)](https://claude.ai/public/artifacts/1921e117-1ea7-41d9-aefb-c5beb03b1c6b)


