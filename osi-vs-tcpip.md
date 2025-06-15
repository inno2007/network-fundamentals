# OSI Model vs TCP/IP Stack

Network communication follows a layered approach where each layer serves a specific function and communicates with layers above and below it. Two commonly referenced models are:

- The **OSI (Open Systems Interconnection) Model**
- The **TCP/IP Model**

---

## 1. OSI 7-Layer Model

| Layer | Description                          | Example Protocols         |
|--------|--------------------------------------|----------------------------|
| 7 - Application     | End-user interaction             | HTTP, SMTP, DNS            |
| 6 - Presentation    | Data format (encoding, encryption) | SSL, JPEG, ASCII           |
| 5 - Session         | Establish, manage, terminate sessions | RPC, NetBIOS            |
| 4 - Transport       | Reliable delivery, segmentation  | TCP, UDP                   |
| 3 - Network         | Logical addressing and routing   | IP, ICMP                   |
| 2 - Data Link       | MAC addressing, framing          | Ethernet, PPP              |
| 1 - Physical        | Bit-level transmission           | Fiber, Copper, 802.11      |

---

## 2. TCP/IP 5-Layer Model (Practical Internet Model)

| Layer       | Corresponds To OSI Layer(s)     | Responsibilities                    |
|-------------|----------------------------------|-------------------------------------|
| Application | 7, 6, 5                          | Network apps, file/email transfers |
| Transport   | 4                                | End-to-end communication, ports     |
| Network     | 3                                | Routing, addressing (IP)           |
| Data Link   | 2                                | Frame transfer over link            |
| Physical    | 1                                | Signals and media                   |

---

## 3. Encapsulation Process

When sending data from sender to receiver:

1. Application Layer creates data.
2. Transport Layer breaks it into **segments**, adds TCP/UDP headers.
3. Network Layer wraps it in **packets** with IP headers.
4. Data Link Layer encapsulates it into **frames** with MAC addresses.
5. Physical Layer converts it into bits and transmits via medium.

### Example Data Unit at Each Layer

| OSI Layer     | Name of Data Unit |
|---------------|-------------------|
| Application   | Data              |
| Transport     | Segment (TCP) or Datagram (UDP) |
| Network       | Packet            |
| Data Link     | Frame             |
| Physical      | Bits              |

---

## 4. Protocol Layer Services

| Layer        | Key Services Provided |
|--------------|------------------------|
| Application  | Interface to user programs |
| Transport    | Reliable or fast data transfer |
| Network      | Logical addressing and routing |
| Data Link    | MAC addressing, error detection |
| Physical     | Signal transmission over media |

---

## 5. OSI vs TCP/IP – Key Differences

| OSI Model                   | TCP/IP Stack                      |
|-----------------------------|-----------------------------------|
| 7 layers                    | 5 layers                          |
| Theoretical/reference model| Practical implementation          |
| Developed by ISO            | Developed by DARPA/DoD            |
| Emphasizes strict layering | Layers often overlap              |

---

## Summary

- The OSI model helps understand network layer functionality, but TCP/IP is used in real-world Internet architecture.
- Encapsulation adds headers (and footers) at each layer for proper delivery.
- Each layer communicates only with its immediate upper/lower layer and its peer layer on the receiving device.

