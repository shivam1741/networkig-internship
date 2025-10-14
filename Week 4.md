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




