# Routing and Switching: Core Concepts

Routing and switching are fundamental aspects of network infrastructure, responsible for directing traffic between devices and networks. This note covers key routing and switching concepts.

## Routing

Routing is the process of selecting the best path for data packets to travel from source to destination across one or more networks. Routers are devices that perform this function.

### Routing Protocols

Routing protocols enable routers to dynamically learn about network topology and make informed decisions about the best paths for data transmission.

- **Distance Vector Protocols:** Routers share their routing table with neighboring routers. These protocols calculate the best path based on the distance (hop count) and direction to destination networks.
  - **RIP (Routing Information Protocol):** An older protocol that uses hop count as the metric. It's simple but has limitations in larger networks.
- **Link-State Protocols:** Routers maintain a complete map of the network topology. They exchange information about the state of their links with all other routers in the network.
  - **OSPF (Open Shortest Path First):** A more advanced protocol that uses link state information to calculate the shortest path. It's more efficient and scalable than distance vector protocols.
- **Path Vector Protocols:** Routers share information about the paths to reach destination networks, including the autonomous systems (AS) the paths traverse.
  - **BGP (Border Gateway Protocol):** The routing protocol used on the internet to exchange routing information between autonomous systems.

### Routing Tables

A routing table is a database stored in a router that contains information about the paths to reach various networks. It includes:

- **Destination Network:** The IP address of the destination network.
- **Next Hop:** The IP address of the next router to forward the packet to.
- **Metric:** A value indicating the "cost" of using a particular route.
- **Interface:** The router interface through which the packet should be sent.

### Static vs. Dynamic Routing

- **Static Routing:** Routes are manually configured by the network administrator. It's simple but requires manual updates when the network topology changes.
- **Dynamic Routing:** Routes are automatically learned and updated by routing protocols. It's more complex but adapts to network changes dynamically.

## Switching

Switching is the process of forwarding data packets between devices within the same network (LAN). Switches operate at Layer 2 (Data Link Layer) of the OSI model.

### MAC Addresses

Switches use MAC (Media Access Control) addresses to identify devices on the local network. Each network interface card (NIC) has a unique MAC address assigned by the manufacturer.

### Switching Table (MAC Address Table)

A switching table is a database stored in a switch that maps MAC addresses to switch ports. When a switch receives a frame, it examines the destination MAC address and forwards the frame out of the port associated with that MAC address.

### VLANs (Virtual LANs)

VLANs are logically separate networks within a physical network. They allow you to group devices into different broadcast domains, improving network security and performance.

### Spanning Tree Protocol (STP)

STP is a protocol that prevents loops in a switched network. Loops can cause broadcast storms and disrupt network communication. STP disables redundant paths in the network, ensuring that there is only one active path between any two devices.

## Key Differences Between Routers and Switches

| Feature           | Router                                                                              | Switch                                                                                |
| :---------------- | :---------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------ |
| Layer             | Layer 3 (Network Layer)                                                             | Layer 2 (Data Link Layer)                                                             |
| Addressing        | IP Addresses                                                                        | MAC Addresses                                                                         |
| Function          | Connects different networks, forwards packets based on IP addresses.                | Connects devices within the same network, forwards frames based on MAC addresses.     |
| Routing           | Uses routing protocols to determine the best path for data transmission.            | Does not use routing protocols, relies on MAC address table for forwarding decisions. |
| Broadcast Domains | Breaks up broadcast domains (each router interface is a separate broadcast domain). | Operates within a single broadcast domain (unless VLANs are configured).              |

## Common Protocols & Technologies

| Protocol/Technology | Description                                                                                   | Layer     | Use Case                                                        |
| :------------------ | :-------------------------------------------------------------------------------------------- | :-------- | :-------------------------------------------------------------- |
| RIP                 | Routing Information Protocol; a distance-vector routing protocol.                             | Layer 3   | (Legacy) Small networks, simple routing.                        |
| OSPF                | Open Shortest Path First; a link-state routing protocol.                                      | Layer 3   | Medium to large networks, efficient and scalable routing.       |
| BGP                 | Border Gateway Protocol; a path-vector routing protocol used between autonomous systems.      | Layer 3   | Internet routing, connecting different networks.                |
| VLAN                | Virtual LAN; a logical grouping of devices within a physical network.                         | Layer 2   | Network segmentation, improving security and performance.       |
| STP                 | Spanning Tree Protocol; prevents loops in a switched network.                                 | Layer 2   | Ensuring a loop-free topology in a switched network.            |
| ARP                 | Address Resolution Protocol; translates IP addresses to MAC addresses within a local network. | Layer 2/3 | Discovering the MAC address associated with a given IP address. |

---

Understanding routing and switching is essential for designing, configuring, and troubleshooting network infrastructure.
