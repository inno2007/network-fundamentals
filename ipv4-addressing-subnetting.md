# IPv4 Addressing and Subnetting

IPv4 addressing is fundamental to identifying devices on a network. Subnetting allows a single network to be divided into smaller logical segments.

---

## 1. What Is an IPv4 Address?

- A **32-bit binary** number represented in **dotted decimal** format (e.g., `192.168.1.1`)
- Divided into **network** and **host** parts.
- Every device on the Internet or LAN must have a **unique IP address**.

---

## 2. IP Address Classes (Legacy)

| Class | Range         | Default Subnet Mask | Usage               |
|-------|---------------|---------------------|---------------------|
| A     | 1.0.0.0 – 126.0.0.0 | 255.0.0.0           | Large networks       |
| B     | 128.0.0.0 – 191.255.0.0 | 255.255.0.0       | Medium networks      |
| C     | 192.0.0.0 – 223.255.255.0 | 255.255.255.0   | Small networks       |
| D     | 224.0.0.0 – 239.255.255.255 | n/a           | Multicast            |
| E     | 240.0.0.0 – 255.255.255.255 | n/a           | Research/reserved    |

---

## 3. Subnet Masks

- A **subnet mask** separates the **network** and **host** parts.
- Written in dotted decimal or CIDR format:
  - `255.255.255.0` = `/24`
  - `255.255.0.0` = `/16`

### CIDR Notation:
- `192.168.1.0/24` means:
  - First 24 bits = network portion
  - Last 8 bits = host portion

---

## 4. Private IP Address Ranges

These are **not routable on the public Internet** and used within LANs.

| Class | Range               |
|-------|---------------------|
| A     | `10.0.0.0/8`        |
| B     | `172.16.0.0/12`     |
| C     | `192.168.0.0/16`    |

---

## 5. Subnetting: How It Works

Subnetting divides a network into **smaller sub-networks** to improve routing and manageability.

### Example:

- Given network: `192.168.1.0/24`
- Subnet mask: `255.255.255.0`
- Want 4 subnets → Need 2 extra bits:
  - `2^2 = 4` subnets
  - New subnet mask = `/26` = `255.255.255.192`
  - Each subnet has 64 addresses, 62 usable

| Subnet # | Network Address | First Usable | Last Usable | Broadcast |
|----------|------------------|---------------|-------------|-----------|
| 1        | 192.168.1.0      | 192.168.1.1   | 192.168.1.62 | 192.168.1.63 |
| 2        | 192.168.1.64     | 192.168.1.65  | 192.168.1.126| 192.168.1.127 |
| …        | …                | …             | …           | …         |

---

## 6. DHCP vs Static Addressing

| Method      | Description |
|-------------|-------------|
| **DHCP**    | Dynamic Host Configuration Protocol assigns IPs automatically. |
| **Static**  | Manually assigned, fixed IPs used for servers or routers. |

---

## 7. Binary Math in Subnetting

Always convert to binary when unsure:

```
IP Address:    192.168.1.0  → 11000000.10101000.00000001.00000000  
Subnet Mask:   255.255.255.192 → 11111111.11111111.11111111.11000000  
```

ANDing them gives:
```
11000000.10101000.00000001.00000000  
&  
11111111.11111111.11111111.11000000  
=  
11000000.10101000.00000001.00000000 → Network Address
```

---

## Summary

| Concept         | Key Idea                         |
|------------------|----------------------------------|
| IP Address       | Identifies host/network location |
| Subnet Mask      | Separates network and host bits  |
| CIDR             | Compact subnet notation (`/24`)  |
| Subnetting       | Divides networks into segments   |
| DHCP             | Dynamic addressing               |
