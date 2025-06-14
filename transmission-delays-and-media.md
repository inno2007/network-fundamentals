# Transmission Delays and Physical Media

This section covers the types of delays a packet experiences as it travels through a network and the physical media that determine the speed and quality of transmission.

---

## 1. Types of Packet-Switched Network Delays

When data travels from source to destination, it experiences **four types of delays** at each router or node:

### a. Processing Delay
- Time to examine packet header and determine output path.
- Usually a few microseconds.

### b. Queuing Delay
- Time the packet spends in the output queue waiting to be transmitted.
- Highly variable depending on traffic intensity.

> **Factors Affecting Queuing Delay**:
> - Arrival rate of packets
> - Burstiness of traffic
> - Transmission rate (R)
> - Queue length and capacity

### c. Transmission Delay
- Time to push all bits of the packet onto the link.
- Depends on:
  - Packet length (L) in bits
  - Transmission rate (R) in bits per second  
- **Formula**: `Transmission Delay = L / R`

> **Example**:  
> L = 1000 bits, R = 100,000 bits/s  
> Delay = 1000 / 100,000 = 0.01 seconds (10 ms)

### d. Propagation Delay
- Time it takes for the bits to travel from one node to the next.
- Depends on:
  - Distance between routers (d)
  - Propagation speed of the medium (s)
- **Formula**: `Propagation Delay = d / s`

---

## 2. End-to-End Delay

The **Total Nodal Delay** at a router is:
```
d_nodal = d_proc + d_queue + d_trans + d_prop
```

Where:
- `d_proc` = Processing delay
- `d_queue` = Queuing delay
- `d_trans` = Transmission delay
- `d_prop` = Propagation delay

> ⚠️ If the network is busy and buffer overflows, **packet loss** can occur.

---

## 3. Throughput

### a. Instantaneous Throughput
- Rate of data transfer at a specific moment.

### b. Average Throughput
- Over a longer interval of time.

### c. Bottleneck Link
- The slowest link in the path determines the overall throughput.

> **Example**:  
> Server to Router = 10 Mbps  
> Router to Client = 5 Mbps  
> → Throughput = **5 Mbps**

---

## 4. Physical Transmission Media

### a. Guided Media (Wired)

| Medium          | Description |
|------------------|-------------|
| **Twisted Pair Copper Wire** | Low cost, up to 10 Gbps, used in LANs (e.g., Cat6). |
| **Coaxial Cable** | Shared access (TV, Internet), higher speeds than twisted pair. |
| **Fiber Optic Cable** | Uses light pulses, supports >100 Gbps, ideal for long distances. |

### b. Unguided Media (Wireless)

| Medium             | Description |
|--------------------|-------------|
| **Terrestrial Radio** | Short to long range (Bluetooth, Wi-Fi, 4G/5G). |
| **Satellite Radio** | Uses geostationary or LEO satellites; high-speed in remote areas. |

---

## 5. Summary Table

| Delay Type        | Depends On                          | Formula / Note |
|-------------------|-------------------------------------|----------------|
| Processing Delay  | Router CPU speed                    | Typically small |
| Queuing Delay     | Network traffic, buffer size        | Varies per packet |
| Transmission Delay| Packet size / link bandwidth        | `L / R` |
| Propagation Delay | Distance / propagation speed        | `d / s` |
| Total Delay       | All delays added per hop            | `d_total = sum of all` |

---
