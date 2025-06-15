# Application Layer Protocols

The application layer is the top layer of both the OSI and TCP/IP models. It enables user-level applications (like browsers and email clients) to interact over the Internet using standard protocols.

---

## 1. Client-Server vs Peer-to-Peer Models

| Architecture      | Description |
|-------------------|-------------|
| **Client-Server** | One centralized server provides resources/services to multiple clients (e.g., Web, Email). |
| **Peer-to-Peer (P2P)** | Peers act as both clients and servers (e.g., BitTorrent, Skype). |

---

## 2. HTTP (HyperText Transfer Protocol)

- Protocol used for accessing web content.
- Runs over TCP, default port 80 (HTTPS uses port 443).
- Stateless — server doesn’t store client state between requests.

### Types of HTTP Connections

| Type              | Description |
|-------------------|-------------|
| **Non-persistent** | Each request/response pair opens a new TCP connection. |
| **Persistent**     | Multiple requests/responses share a single connection. |

### HTTP Methods:
- `GET`: Retrieve resource
- `POST`: Submit data to server
- `HEAD`: Retrieve header only
- `PUT`, `DELETE`: Modify server resources

### Cookies:
- Used to maintain **session state**
- Stored on client, associated with requests

### Conditional GET:
Used for caching and minimizing data transfer.

```http
If-Modified-Since: Wed, 10 Apr 2024 10:00:00 GMT
```

If resource hasn't changed, server returns `304 Not Modified`.

---

## 3. Web Caching

- Reduces load on origin servers and speeds up delivery.
- Stores frequently requested pages at intermediate caches (proxy servers or browsers).
- Cache checks freshness before serving stored content.

---

## 4. DNS (Domain Name System)

**Purpose**: Resolves human-readable domain names into IP addresses.

### Components:

| Component      | Role |
|----------------|------|
| **Root DNS**   | Knows addresses of TLD (Top-Level Domain) servers. |
| **TLD Server** | Responsible for domains like `.com`, `.edu`, `.org`. |
| **Authoritative DNS** | Provides IP for specific domain (e.g., `google.com`). |
| **Local Resolver** | Typically operated by your ISP. Queries root → TLD → authoritative. |

### Query Types:

| Query Type       | Description |
|------------------|-------------|
| **Recursive**    | DNS server must resolve full query and return result. |
| **Iterative**    | Server responds with next step in resolution process. |

---

## 5. Email Protocols

| Protocol | Description |
|----------|-------------|
| **SMTP** (Simple Mail Transfer Protocol) | Used to **send** email from client to server or server to server. |
| **POP3** (Post Office Protocol v3)       | Download-and-delete model (emails removed from server after retrieval). |
| **IMAP** (Internet Message Access Protocol) | Allows client to **view** and manage messages on server (better for multiple devices). |

SMTP uses TCP, typically port 25.

---

## 6. Summary Table

| Protocol | Purpose           | Transport Layer | Port |
|----------|-------------------|------------------|------|
| HTTP     | Web content        | TCP              | 80 / 443 |
| DNS      | Name resolution    | UDP / TCP        | 53 |
| SMTP     | Sending mail       | TCP              | 25 |
| POP3     | Receiving mail     | TCP              | 110 |
| IMAP     | Managing mail      | TCP              | 143 |

---

