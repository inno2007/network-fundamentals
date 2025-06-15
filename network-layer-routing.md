# Network Layer: Routing and Packet Forwarding

The network layer is responsible for moving packets from the source host to the destination host, across potentially multiple networks. It determines **where to send each packet** and **how to get it there efficiently**.

---

## 1. Key Functions of the Network Layer

| Function       | Description |
|----------------|-------------|
| **Forwarding** | Moving packets from router input to appropriate output port. |
| **Routing**    | Determining the optimal path for packets across the network. |
| **Addressing** | Assigning and interpreting logical addresses (e.g., IPv4, IPv6). |

---

## 2. Forwarding vs Routing

| Task        | Focus                   | Time Scale       |
|-------------|--------------------------|------------------|
| **Forwarding** | Local router decision (per packet) | Fast (microseconds) |
| **Routing**    | Global path determination (per flow) | Slower (seconds/minutes) |

---

## 3. Inside a Router

A typical router includes the following components:

### a. Input Ports
- Receives packets
- Performs lookup to determine next-hop destination
- Passes packet to switching fabric

### b. Switching Fabric
- Transfers packets between input and output ports
- Can be:
  - **Memory-based**
  - **Bus-based**
  - **Crossbar-based**

### c. Output Ports
- Buffer packets if output link is busy
- Schedules packet transmission

---

## 4. Queuing and Scheduling

### a. Queuing
Occurs when multiple packets need to use the same output port.

| Type               | Description |
|--------------------|-------------|
| **Input Queuing**  | Packets wait at input ports |
| **Output Queuing** | Packets wait at output ports |
| **Head-of-Line (HOL) Blocking** | First packet delays others |

### b. Scheduling Algorithms

| Algorithm   | Description |
|-------------|-------------|
| **FIFO**    | First In, First Out |
| **Priority Queuing** | Higher-priority packets go first |
| **Round Robin** | Fair access by rotating through flows |
| **Weighted Fair Queuing (WFQ)** | Allocates bandwidth based on assigned weights |

---

## 5. Packet Filtering and Firewalls

Network-layer devices can also:
- Drop suspicious packets (filtering)
- Enforce access rules (firewalls)

---

## 6. Summary

| Component      | Role                                  |
|----------------|----------------------------------------|
| Router         | Directs traffic between networks       |
| Input Port     | Packet arrival and lookup              |
| Switching Fabric | Internal transfer path              |
| Output Port    | Buffering and scheduling               |
| Routing        | Global logic for best paths            |
| Forwarding     | Local per-packet decision              |

