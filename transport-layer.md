# Transport Layer: TCP vs UDP

The transport layer provides **end-to-end communication** between processes running on different hosts. It is responsible for delivering messages reliably (or not), in the correct order, and with proper error checking.

---

## 1. Responsibilities of the Transport Layer

- **Process-to-process delivery** (via ports)
- **Multiplexing/Demultiplexing**
- **Reliable data transfer**
- **Error detection**
- **Flow control**
- **Congestion control**

---

## 2. Multiplexing & Demultiplexing

- **Multiplexing**: Collects data from multiple sockets (applications) and adds header information.
- **Demultiplexing**: Uses destination port numbers to deliver data to the correct receiving process.

Each message uses a **source IP + source port** and **destination IP + destination port**.

---

## 3. UDP (User Datagram Protocol)

| Feature               | Description |
|------------------------|-------------|
| **Connectionless**     | No handshake or setup |
| **Unreliable**         | No ACKs, retransmissions, or ordering |
| **Low overhead**       | Faster for simple apps |
| **Used for**           | Streaming, VoIP, DNS, online games |
| **Header Size**        | 8 bytes |

### Advantages:
- Fast and efficient
- Ideal for time-sensitive apps

### Disadvantages:
- No guarantee of delivery or order
- No congestion or flow control

---

## 4. TCP (Transmission Control Protocol)

| Feature               | Description |
|------------------------|-------------|
| **Connection-oriented**| Uses 3-way handshake to establish connection |
| **Reliable delivery**  | ACKs, sequence numbers, retransmission |
| **In-order delivery**  | Packets arrive in the order sent |
| **Flow & congestion control** | Maintains stable, fair usage of bandwidth |
| **Header Size**        | 20 bytes (minimum) |

---

## 5. TCP Connection Establishment: 3-Way Handshake

1. **Client → Server**: `SYN`
2. **Server → Client**: `SYN-ACK`
3. **Client → Server**: `ACK`

Once established, data can flow bidirectionally.

---

## 6. Reliable Data Transfer in TCP

- Uses **sequence numbers** to label bytes in the stream.
- Receiver sends **ACKs** for successfully received segments.
- Missing segments are **retransmitted**.
- If duplicate ACKs are detected → fast retransmit triggered.

---

## 7. Flow Control

TCP uses a **receiver window (rwnd)** to ensure the sender doesn't overwhelm the receiver.

- Receiver advertises available buffer space.
- Sender adjusts sending rate based on rwnd.

---

## 8. Congestion Control

TCP also avoids **overloading the network** using algorithms like:

| Algorithm      | Behavior |
|----------------|----------|
| **Slow Start** | Gradually increases transmission rate |
| **AIMD**       | Additive Increase, Multiplicative Decrease |
| **Fast Retransmit** | Triggers early retransmission before timeout |

---

## 9. Summary

| Feature       | TCP                       | UDP                     |
|---------------|----------------------------|--------------------------|
| Reliability   | Yes (ACKs, retransmissions)| No                       |
| Ordering      | Yes                        | No                       |
| Overhead      | Higher                     | Lower                    |
| Use Cases     | File transfer, web, email  | Video streaming, VoIP    |
