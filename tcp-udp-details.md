# TCP & UDP: Transport Layer Details

This file dives deeper into **TCP's reliable delivery mechanisms**, **congestion control**, **flow control**, and compares it with the simpler **UDP** protocol.

---

## 1. TCP Reliable Data Transfer

TCP ensures data arrives **completely and in order** using:

| Mechanism        | Description |
|------------------|-------------|
| **Sequence Numbers** | Identify each byte; used to reorder out-of-sequence packets. |
| **Acknowledgments (ACKs)** | Receiver confirms receipt of data. |
| **Retransmission** | Sender resends lost or corrupted segments. |
| **Checksum** | Detects bit-level errors in segments. |

---

## 2. TCP Timers

- **Estimated RTT** is calculated based on recent samples:
  ``` 
  EstimatedRTT = (1 - α) × EstimatedRTT + α × SampleRTT  
  ```
  (Typical α = 0.125)

- **TimeoutInterval**:
  ```
  Timeout = EstimatedRTT + 4 × DevRTT
  ```

- Retransmission triggered if ACK not received within timeout.

---

## 3. TCP Flow Control

Uses **Receiver Window (rwnd)** to:
- Prevent overwhelming a slower receiver
- Ensures sender pauses if buffer is full

Receiver includes current `rwnd` in every ACK.

---

## 4. TCP Congestion Control

Helps avoid overloading the network:

### a. Slow Start
- Begins with a small congestion window (cwnd).
- cwnd doubles each RTT until threshold is hit.

### b. Congestion Avoidance
- After threshold is reached, cwnd grows linearly.

### c. Fast Retransmit & Fast Recovery
- If **3 duplicate ACKs** received → retransmit segment immediately.
- cwnd is reduced (multiplicative decrease).

---

## 5. TCP Full Duplex

- Data can flow in both directions **simultaneously** over a single connection.
- Each side maintains separate **sequence** and **acknowledgment** numbers.

---

## 6. UDP Checksum & Characteristics

UDP is connectionless and does not:
- Ensure delivery
- Ensure ordering
- Provide flow or congestion control

### Checksum:
- Optional in UDP.
- Verifies integrity of the data (but not retransmitted if corrupted).

---

## 7. TCP vs UDP – Key Differences

| Feature         | TCP                               | UDP                    |
|------------------|------------------------------------|------------------------|
| Connection Setup | 3-way handshake                    | None                   |
| Reliability      | Guaranteed (ACKs, retransmits)     | None                   |
| Ordering         | Yes                                | No                     |
| Speed            | Slower                             | Faster                 |
| Use Cases        | File transfer, web, email          | Streaming, VoIP, DNS   |

---

## Summary

TCP provides:
- Ordered, reliable delivery
- Flow and congestion control
- Timeout and retransmission logic

UDP is:
- Lightweight and fast
- Ideal for real-time, loss-tolerant applications

