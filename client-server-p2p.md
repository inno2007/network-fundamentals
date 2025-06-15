# Client-Server and Peer-to-Peer Architecture

This section covers the architectural models that define how hosts and applications interact on the Internet: **Client-Server** and **Peer-to-Peer (P2P)**. It also introduces port numbers and socket communication.

---

## 1. Client-Server Model

In the **Client-Server** model:
- A **server** is always-on and provides services.
- A **client** initiates requests to the server.
- The server usually has a fixed IP address.

### Examples:
- Web (HTTP): Browser (client) requests pages from a web server.
- Email (SMTP/IMAP): Client sends or retrieves mail from a mail server.

### Advantages:
- Centralized control
- Easier to manage security and backup

### Disadvantages:
- Server can become a bottleneck
- Single point of failure

---

## 2. Peer-to-Peer (P2P) Model

In a **P2P** architecture:
- Hosts (peers) act as both **clients and servers**.
- No always-on server — peers communicate directly.
- System scales better with more users.

### Examples:
- BitTorrent
- Skype
- Blockchain nodes

### Advantages:
- Scalable
- Efficient bandwidth utilization

### Disadvantages:
- Harder to manage
- Security and consistency challenges

---

## 3. Port Numbers and Processes

- Each process running on a host is identified by a **port number**.
- Together with IP address, a **socket** identifies a specific process on a network.

| Example Application | Protocol | Default Port |
|---------------------|----------|--------------|
| HTTP                | TCP      | 80           |
| HTTPS               | TCP      | 443          |
| SMTP                | TCP      | 25           |
| DNS                 | UDP      | 53           |

---

## 4. Socket Communication

- A **socket** is the interface between the application layer and the transport layer.
- Used for sending/receiving messages between client and server.

### Server-Side Flow:
1. Create a socket
2. Bind it to an IP and port
3. Listen for connections
4. Accept incoming client

### Client-Side Flow:
1. Create a socket
2. Connect to the server's IP and port
3. Send/receive data

---

## 5. Summary

| Model       | Key Features                     | Use Cases               |
|-------------|----------------------------------|--------------------------|
| Client-Server | Centralized, stable, secure      | Web, email, banking     |
| Peer-to-Peer | Decentralized, scalable, flexible| File sharing, VoIP      |

