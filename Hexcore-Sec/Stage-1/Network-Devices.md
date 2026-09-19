# Network Security Fundamentals

Understanding networking is essential in cybersecurity. It helps us understand how devices communicate, how traffic moves across a network, and how to investigate network activity during security audits and incidents.

The main topics covered are:

* OSI / TCP-IP Model
* IP Addressing & Subnetting
* Switching
* Routing

---

## 1. Network Fundamentals

A **network** is a group of connected devices that can communicate with each other.

For example:

```text
Computer ── Switch ── Router ── Internet
```

Each device has a role in allowing data to move from one host to another.

### Host

A **host** is any device that can send or receive data over a network.

Examples include computers, servers, phones, IP phones, and IoT devices.

A host can act as either a **client or a server depending on the communication taking place**.

For example, when a browser requests a webpage:

```text
Browser (Client) ──────> Web Server
```

The browser is the client because it is requesting a service, while the web server is the server because it provides that service.

However, the web server might request a file from a file server:

```text
Web Server (Client) ──────> File Server
```

The same host can therefore be a client in one communication and a server in another.

---

## 2. IP Address

An **IP address** is a logical address used to identify a host or network interface for IP communication.

An IPv4 address is **32 bits**, divided into four 8-bit octets.

For example:

```text
192.168.1.236
```

In binary:

```text
11000000.10101000.00000001.11101100
```

Each octet can contain a value from **0 to 255**.

The important thing to understand at this stage is that an IP address helps determine **where a host is located within an IP network and where traffic should be delivered**.

---

## 3. Network

A network provides a way for hosts to communicate.

Hosts that belong to the same network can generally communicate directly at the local network level, while communication with another network requires a router.

For example:

```text
Network A
PC1 ── Switch ── PC2
          │
        Router
          │
Network B
       Server
```

This distinction is important:

> **Switches primarily connect devices within a network, while routers connect different networks.**

A network can also be divided into smaller networks called **subnets**. Subnetting is useful for organizing networks, controlling traffic, and improving security.

---

# 4. Network Devices

## Repeater

A **repeater** regenerates a network signal so that it can travel a greater distance.

Its main concern is the **signal**, not the destination of the traffic.

```text
Host ───── Repeater ───── Host
```

**Key idea:** Repeater → extends/regenerates signals.

---

## Hub

A **hub** is essentially a multi-port repeater.

When a hub receives data, it sends it out through its other ports rather than determining which specific host should receive it.

```text
        PC1
         │
PC2 ─── Hub ─── PC3
         │
        PC4
```

Because of this behavior, hubs are inefficient compared with switches and are largely obsolete in modern networks.

**Key idea:** Hub → sends traffic to all connected ports.

---

## Bridge

A **bridge** connects network segments and uses **MAC addresses** to determine whether traffic needs to cross from one segment to another.

It can therefore reduce unnecessary traffic between network segments.

**Key idea:** Bridge → connects and filters Layer 2 segments.

---

## Switch

A **switch** connects multiple hosts within a network and forwards Ethernet frames based on **MAC addresses**.

The switch learns which MAC address is connected to which port and stores this information in a **MAC address table**.

For example:

```text
MAC Address          Port
AA:AA:AA:AA:AA:AA    1
BB:BB:BB:BB:BB:BB    2
CC:CC:CC:CC:CC:CC    3
```

If a frame is destined for a known MAC address, the switch can send it directly to the appropriate port instead of sending it everywhere.

**Key idea:** Switch → forwards frames within a network using MAC addresses.

---

## Router

A **router** connects different networks and forwards IP packets between them.

For example:

```text
192.168.1.0/24
       │
     Switch
       │
     Router
       │
     Switch
       │
192.168.2.0/24
```

The router needs to know where different networks can be reached. It stores this information in a **routing table**.

A simplified routing table might look like:

```text
Destination Network     Route
192.168.1.0/24          Local
192.168.2.0/24          Local
10.0.0.0/8              Via another router
0.0.0.0/0               Default route
```

When a packet arrives, the router examines its destination IP address and uses the routing table to determine where to send it next.

---

# 5. Default Gateway

A **default gateway** is the device a host sends traffic to when the destination is outside its local network.

For example:

```text
PC
IP Address:      192.168.1.50
Default Gateway: 192.168.1.1
```

If the PC wants to communicate with another host on its local network, it can communicate directly.

If it wants to reach a different network:

```text
PC ──> Default Gateway ──> Other Network
```

The default gateway is usually the IP address of a router interface on the host's local network.

---

# 6. Switching vs Routing

This is one of the most important concepts to remember.

### Switching

**Switching is the process of forwarding frames within a network.**

```text
PC1 ── Switch ── PC2
```

Switches primarily use **MAC addresses**.

### Routing

**Routing is the process of forwarding packets between different networks.**

```text
Network A ── Router ── Network B
```

Routers primarily use **IP addresses and routing tables**.

### Remember

> **Switching → within the network**

> **Routing → between networks**

---

# 7. Why This Matters in Network Security

Network security depends on understanding where traffic comes from, where it is going, and how it moves through the network.

For example, a security log might show:

```text
Source IP:      192.168.1.50
Destination IP: 10.10.20.5
Protocol:       TCP
Destination Port: 443
```

To investigate this properly, you need to understand:

* Which host owns `192.168.1.50`?
* Is `10.10.20.5` on the same network?
* Which router handles the traffic?
* What protocol is being used?
* What service is running on port `443`?
* Where should this traffic normally go?

This is why networking fundamentals are an important foundation for **network monitoring, log analysis, incident response, and security auditing**.

---

# Key Takeaways

```text
Host
└── Sends and receives network data

IP Address
└── Provides logical addressing

Repeater
└── Regenerates signals

Hub
└── Sends traffic to connected ports

Bridge
└── Connects and filters network segments

Switch
└── Forwards frames using MAC addresses

Router
└── Forwards packets between networks

Default Gateway
└── Provides a path to other networks

Switching
└── Communication within a network

Routing
└── Communication between networks
```
