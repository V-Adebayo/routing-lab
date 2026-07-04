# Routing Basics

## What is Routing?

Routing is the process of moving data packets from one network to another. A router looks at the destination IP address of a packet and decides the best path to send it.

Without routing, devices on different networks would not be able to communicate.

---

## What is a Router?

A router is a Layer 3 (Network Layer) device that connects different networks together.

Its main job is to:
- Forward packets between networks
- Choose the best path for traffic
- Maintain a routing table
- Prevent unnecessary traffic from being broadcast to every network

Example:

PC A (192.168.1.10) → Router → PC B (192.168.2.20)

---

# How Routing Works

1. A device creates a packet.
2. It checks if the destination is on the same network.
3. If it is, the packet is sent directly.
4. If not, the packet is sent to the default gateway (router).
5. The router checks its routing table.
6. The router forwards the packet to the next network.
7. The process continues until the packet reaches its destination.

---

# Routing Table

A routing table is like a map used by a router.

It contains information such as:
- Destination network
- Next hop
- Exit interface
- Metric (cost)

The router always checks this table before forwarding a packet.

Example:

| Destination Network | Next Hop | Interface |
|---------------------|----------|-----------|
| 192.168.1.0/24 | Connected | Gig0/0 |
| 192.168.2.0/24 | Connected | Gig0/1 |
| 0.0.0.0/0 | 10.0.0.1 | Serial0/0 |

---

# Default Gateway

A default gateway is the router that a device sends traffic to when the destination is on another network.

Example:

PC IP:
```
192.168.1.50
```

Default Gateway:
```
192.168.1.1
```

Whenever the PC wants to reach another network, it sends the packet to **192.168.1.1**.

---

# Types of Routing

## 1. Static Routing

The network administrator manually enters routes into the router.

### Advantages
- Simple for small networks
- More secure
- Uses fewer router resources

### Disadvantages
- Time-consuming
- Doesn't adjust automatically if a link fails
- Difficult to manage in large networks

---

## 2. Dynamic Routing

Routers automatically learn routes by exchanging routing information with other routers.

Common dynamic routing protocols:
- RIP
- OSPF
- EIGRP
- IS-IS
- BGP

### Advantages
- Automatically updates routes
- Better for large networks
- Handles network changes

### Disadvantages
- Uses more CPU and memory
- More complex to configure

---

# Routing Protocols

Routing protocols help routers share network information.

### RIP (Routing Information Protocol)

- Uses hop count
- Maximum hop count is 15
- Simple to configure
- Best for small networks

---

### OSPF (Open Shortest Path First)

- Uses cost as its metric
- Converges faster than RIP
- Common in enterprise networks
- Supports large networks

---

### EIGRP

- Developed by Cisco
- Uses bandwidth and delay to calculate the best path
- Fast convergence
- Mostly used in Cisco environments

---

### BGP (Border Gateway Protocol)

- Used between different organizations and Internet Service Providers (ISPs)
- Makes routing decisions based on policies
- Used on the Internet

---

# Routing Metrics

A metric is a value used by routing protocols to decide the best path.

Different protocols use different metrics.

Examples:
- Hop count
- Bandwidth
- Delay
- Cost
- Reliability

Normally, the route with the lowest metric is preferred.

---

# Administrative Distance (AD)

Administrative Distance is the level of trust assigned to a route.

If a router learns the same route from multiple sources, it chooses the one with the lowest AD.

Some common values:

| Route Source | AD |
|--------------|---:|
| Connected | 0 |
| Static | 1 |
| EIGRP | 90 |
| OSPF | 110 |
| RIP | 120 |

Lower AD = More trusted.

---

# Packet Forwarding

When a router receives a packet:

1. Reads the destination IP address.
2. Searches the routing table.
3. Finds the best matching route.
4. Sends the packet out through the correct interface.

---


#  Summary

- Routing moves packets between different networks.
- Routers make forwarding decisions using routing tables.
- Static routes are manually configured.
- Dynamic routes are learned automatically.
- Routing protocols include RIP, OSPF, EIGRP, and BGP.
- Metrics help determine the best path.
- Administrative Distance determines which route source is preferred.
- Every device uses a default gateway to reach remote networks.

---

##  Notes

- Routing happens at **Layer 3 (Network Layer)**.
- A router forwards packets based on the **destination IP address**, not the MAC address.
- Every router keeps a routing table to decide where packets should go.
- If a destination isn't on the local network, the packet is sent to the **default gateway**.
- Static routing is good for small networks, while dynamic routing is better for larger environments.
