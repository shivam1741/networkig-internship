# Day 1(OSPF)

## Open Shortest Path First (OSPF) Protocol

###  Overview

**OSPF (Open Shortest Path First)** is a dynamic routing protocol used within an autonomous system (AS). It is a **link-state routing protocol** that uses **Dijkstra’s algorithm** to calculate the shortest path to each node.

- **Protocol Type**: Interior Gateway Protocol (IGP)
- **Routing Type**: Link-State
- **Standard**: Open standard (defined in RFC 2328)
- **Metric**: Cost (based on bandwidth)



### Key Features

- **Fast Convergence**: Quickly adapts to network changes.
- **Hierarchical Design**: Supports areas to optimize routing.
- **Scalability**: Suitable for large enterprise networks.
- **VLSM & CIDR Support**: Efficient IP address allocation.
- **Multicast Updates**: Uses multicast addresses for routing updates.
- **Authentication Support**: Ensures secure routing updates.



### How OSPF Works

1. **Neighbor Discovery**
   - Routers send **Hello packets** to discover neighbors.
   - Neighbors must agree on parameters (hello/dead intervals, area ID, etc.).

2. **Database Exchange**
   - Routers exchange **Link-State Advertisements (LSAs)**.
   - LSAs describe the state of each router’s links.

3. **Topology Map Creation**
   - Each router builds a **Link-State Database (LSDB)**.
   - The LSDB is identical across routers in the same area.

4. **Shortest Path Calculation**
   - Routers run **Dijkstra’s algorithm** to compute the shortest path tree.
   - Routing tables are built from this tree.



### OSPF Areas

- **Backbone Area (Area 0)**: Central area that connects all other areas.
- **Non-Backbone Areas**: Must connect to Area 0.
- **Stub Areas**: Restrict external route advertisements.
- **Totally Stubby Areas**: Further restrict routing information.
- **Not-So-Stubby Areas (NSSA)**: Allow limited external routes.



### OSPF Packet Types

| Packet Type       | Description                          |
|-------------------|--------------------------------------|
| Hello             | Discover and maintain neighbors      |
| Database Description (DBD) | Summary of LSDB              |
| Link-State Request (LSR)   | Request specific LSAs        |
| Link-State Update (LSU)    | Send LSAs                    |
| Link-State Acknowledgment (LSAck) | Acknowledge LSAs     |


### OSPF Authentication

- **Null Authentication**: No authentication.
- **Plain Text Authentication**: Simple password.
- **MD5 Authentication**: Secure hash-based authentication.



# Day 2(EIGRP)


## Enhanced Interior Gateway Routing Protocol (EIGRP)

### Overview

**EIGRP** is a Cisco proprietary **advanced distance-vector routing protocol** that combines the best features of link-state and distance-vector protocols. It is designed for fast convergence, scalability, and efficient routing in large networks.

- **Protocol Type**: Advanced Distance-Vector
- **Vendor**: Cisco (now partially open via RFC 7868)
- **Metric**: Composite metric (Bandwidth, Delay, Reliability, Load)


### Key Features

- **Fast Convergence**: Uses Diffusing Update Algorithm (DUAL)
- **Loop-Free Routing**: Guaranteed via DUAL
- **Partial Updates**: Only sends updates when topology changes
- **Supports VLSM and CIDR**
- **Multicast Communication**: Uses 224.0.0.10 for updates
- **Unequal Cost Load Balancing**: Can use multiple paths with different metrics



### How EIGRP Works

1. **Neighbor Discovery**
   - Routers send **Hello packets** to discover and maintain neighbors.

2. **Topology Table**
   - Maintains all learned routes, including successors and feasible successors.

3. **DUAL Algorithm**
   - Calculates loop-free paths and backup routes.

4. **Routing Table**
   - Only the best routes (successors) are installed in the routing table.


### EIGRP Metric Formula

EIGRP uses a **composite metric** based on:

- **Bandwidth**
- **Delay**
- (Optionally) Reliability and Load

**Default Metric Formula**:
Metric = [K1 * Bandwidth + K3 * Delay] * 256


Where:
- K1 and K3 are default constants (usually 1)
- Bandwidth is the minimum bandwidth of the path
- Delay is the cumulative delay of the path



### EIGRP Packet Types

| Packet Type | Description                          |
|-------------|--------------------------------------|
| Hello       | Discover and maintain neighbors      |
| Update      | Send routing updates                 |
| Query       | Ask neighbors for route info         |
| Reply       | Respond to queries                   |
| ACK         | Acknowledge receipt of packets       |


### EIGRP Authentication

- Supports **MD5 authentication** for secure routing updates.

