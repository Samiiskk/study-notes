# Day 13 — IP Addressing, Routing & Network Protocols

**Date:** June 16, 2026
**Source:** IBM Cybersecurity Analyst — Network Security &
Database Vulnerabilities (Module 2)

---

## Number Systems in Networking

| System | Base | Digits | Use |
|--------|------|--------|-----|
| Binary | 2 | 0, 1 | How computers store data |
| Octal | 8 | 0-7 | Less common |
| Decimal | 10 | 0-9 | Human readable |
| Hexadecimal | 16 | 0-9, A-F | Compact binary representation |

**Binary to decimal:** Sum values of all positions where bit = 1
**Decimal to binary:** Subtract largest possible power of 2 repeatedly

---

## IPv4 Addressing

**Structure:** 32-bit address divided into 4 octets
Each octet ranges from 0-255 in decimal

**Three parts of an IP address:**
- **Network part** — identifies the network
- **Host part** — identifies the device
- **Subnet number** — divides large networks

### IPv4 Address Classes

| Class | Range | Default Mask | Use |
|-------|-------|-------------|-----|
| A | 0.0.0.0 – 127.255.255.255 | 255.0.0.0 | Large networks |
| B | 128.0.0.0 – 191.255.255.255 | 255.255.0.0 | Medium networks |
| C | 192.0.0.0 – 223.255.255.255 | 255.255.255.0 | Small networks |
| D | 224.0.0.0 – 239.255.255.255 | — | Multicast |
| E | 240.0.0.0 – 255.255.255.255 | — | Experimental |

### IPv4 Limitations
- Supports ~4.3 billion addresses
- Address exhaustion — running out of addresses
- Complex routing
- Security issues — no built-in encryption
- Led to creation of IPv6

---

## IPv4 Header Key Fields

| Field | Purpose |
|-------|---------|
| Protocol version | IPv4 or IPv6 |
| TTL (Time to Live) | Limits packet hops — prevents infinite loops |
| Protocol ID | Identifies data type — TCP, UDP, ICMP |
| Source IP | Where packet came from |
| Destination IP | Where packet is going |
| Payload | The actual message data |

---

## Subnet Masks & Prefixes
- Divides IP address into network and host portions
- **/24 prefix** = first 24 bits are network bits
- **Broadcast address** = all host bits set to 1
  — sends to all devices in subnet
- **Default gateway** = router that forwards packets outside local network

---

## IPv6

**Structure:** 128-bit address, eight groups of four hex digits
separated by colons

**Example:** 2001:0db8:85a3:0000:0000:8a2e:0370:7334

### IPv6 Addressing Types
| Type | Description |
|------|-------------|
| Unicast | One-to-one communication |
| Multicast | One-to-many communication |
| Anycast | One-to-nearest — replaces IPv4 broadcast |

### IPv6 Advantages over IPv4
- Vastly larger address space
- Built-in IPsec for security
- Simpler, more efficient header
- Better Quality of Service (QoS)
- Enhanced mobile device support

---

## MAC Addresses (Layer 2)

- **48 bits** long, divided into 6 octets
- **First 3 octets** = OUI — identifies manufacturer
- **Last 3 octets** = unique card identifier
- Fixed in hardware but **can be spoofed** by attackers

### Finding MAC addresses
- Linux: `ifconfig` or `ip neighbor show`
- Windows: `ipconfig /all`
- ARP table: `arp` (Windows) or `ip neighbor show` (Linux)

---

## Layer 2 vs Layer 3 Addressing

| | Layer 2 | Layer 3 |
|-|---------|---------|
| Address type | MAC address | IP address |
| Purpose | Communication within local network | Routing across different networks |
| Scope | Local segment only | Global routing |
| Example | 00:1A:2B:3C:4D:5E | 192.168.1.100 |

---

## ARP (Address Resolution Protocol)

Maps Layer 3 IP addresses to Layer 2 MAC addresses.

**How ARP works:**
1. Device wants to send data to IP address
2. Broadcasts ARP Request — "Who has this IP?"
3. Device with that IP replies with ARP Reply — "I do, here's my MAC"
4. Requesting device stores mapping in **ARP table**
5. Future packets go directly to that MAC address

**Within same broadcast domain** — use destination MAC directly
**Different broadcast domain** — use MAC of default gateway (router)

---

## Routing Tables

Every network device maintains a routing table to direct packets.

### Types of Routes
| Type | Description |
|------|-------------|
| Default route | Forwards packets to destinations not in routing table |
| Directly connected | Networks directly on router's interfaces |
| Static | Manually configured by administrator |
| Dynamic | Auto-updated by routing protocols |

### Dynamic Routing Protocols
- **OSPF** — Open Shortest Path First
- **RIP** — Routing Information Protocol
- **EIGRP** — Enhanced Interior Gateway Routing Protocol

### Packet Delivery Process
1. Device checks routing table
2. If destination is local → send directly using ARP
3. If destination is remote → send to default gateway
4. Router uses routing table to forward to next hop
5. Process repeats until packet reaches destination
6. Return path must also exist for communication

---

## Broadcast Domains & VLANs
- **Broadcast domain** — network segment where all devices receive broadcasts
- Corresponds to a **VLAN** (Virtual LAN)
- A device can have multiple NICs connected to different broadcast domains
- Each interface has its own IP and MAC address

---

## Key Takeaways
- IPv4 = 32-bit, 4 octets, ~4.3 billion addresses
- IPv6 = 128-bit, 8 groups of hex, vastly more addresses
- MAC addresses work at Layer 2 — local delivery only
- IP addresses work at Layer 3 — routing between networks
- ARP bridges Layer 2 and Layer 3 — maps IP to MAC
- Default gateway = router that handles traffic outside local network
- Routing table = map that tells router where to send packets
- TTL prevents packets from looping forever on the network
- MAC addresses can be spoofed — don't rely on them for security
- Wireshark can capture and analyze all these packet fields
