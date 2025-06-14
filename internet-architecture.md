# Internet Architecture and Network Structure

This section explains how the Internet is structured, how data moves through its components, and how different technologies connect users to the global network.

---

## What Is the Internet?

The Internet can be viewed from two perspectives:

1. **Nuts and Bolts View**:  
   - A global system of hardware (routers, switches, cables) and software (protocols) that connects billions of devices.
   - Data is sent in **packets**, small units of information that travel independently.

2. **Service View**:  
   - Provides applications like websites, email, file transfers, and streaming.
   - Supports interaction between client and server programs across networks.

---

## Key Internet Components

| Component           | Description |
|---------------------|-------------|
| **Hosts / End Systems** | Devices like computers, phones, servers. They generate and receive data. |
| **Routers / Switches** | Forward data packets across networks. |
| **Links**           | Physical/wireless paths connecting devices (e.g., fiber, coaxial, Wi-Fi). |
| **Protocols**       | Rules for communication (e.g., TCP, IP, HTTP, DNS). |
| **ISPs**            | Internet Service Providers connect users and networks to the global Internet. |

---

## Network Edge vs Core

### Network Edge
- Includes **end systems** like phones, PCs, IoT devices.
- Connects to the network via **access networks**:
  - **Home networks** (e.g., via modem/router)
  - **University/corporate LANs**
  - **Mobile networks (3G, 4G, 5G)**

### Network Core
- High-speed **routers and links** that move data across long distances.
- Uses **packet switching** to forward packets toward destinations.

---

## Packet Switching

- Data is broken into **packets** and sent independently across the network.
- Routers store and forward entire packets before sending them to the next hop.
- Advantages:
  - Efficient bandwidth use.
  - Scales well for bursty traffic.
- Disadvantages:
  - Packets can arrive out of order.
  - Queuing delay if router buffers are full.
  - Packet loss if congestion is too high.

---

## Circuit Switching vs. Packet Switching

| Feature            | Circuit Switching        | Packet Switching          |
|--------------------|--------------------------|---------------------------|
| Dedicated Path     | Yes (reserved resources) | No                        |
| Efficient Use      | No (idle paths waste)    | Yes (shared resources)    |
| Used In            | Telephone networks       | Internet                  |
| Examples           | PSTN                     | TCP/IP networks           |

---

## Multiplexing in Circuit Switching

- **FDM (Frequency Division Multiplexing)**: Each connection uses a specific frequency.
- **TDM (Time Division Multiplexing)**: Each gets a dedicated time slot.

---

## Access Network Technologies

| Type        | Description |
|-------------|-------------|
| **DSL**     | Uses copper phone lines, separates voice/data via splitter. |
| **Cable**   | Coaxial cable shares Internet and TV. |
| **FTTH**    | Fiber-to-the-Home, fastest option with dedicated fiber lines. |
| **LAN**     | Uses Ethernet for internal wired networks. |
| **Wi-Fi**   | Wireless LAN using access points. |
| **Mobile (3G-5G)** | Cellular network using radio towers. Shared bandwidth. |

---

## ISP and Internet Hierarchy

- **Tier 1 ISPs**: Backbone providers with global reach.
- **Tier 2 ISPs**: Regional ISPs that lease bandwidth from Tier 1.
- **Tier 3 ISPs**: Local ISPs that connect home and small business users.
- **IXPs (Internet Exchange Points)**: Interconnect ISPs to exchange traffic efficiently.

---

## Key Functions of the Network Core

| Function    | Description |
|-------------|-------------|
| **Forwarding** | Router moves packet from input to correct output link. |
| **Routing**    | Determines the best path across the network using algorithms. |

