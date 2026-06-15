# Day 12 — Computer Networks, Hardware & Protocols

**Date:** June 15, 2026
**Source:** IBM Cybersecurity Analyst — Network Security &
Database Vulnerabilities (Module 1)
**Status:** - Module 1 Complete

---

## Networking Hardware Devices

| Device | Purpose |
|--------|---------|
| Hub | Broadcasts data to ALL devices — inefficient |
| Switch | Forwards data only to intended device using MAC table |
| Router | Connects different networks, forwards packets by IP address |
| Bridge | Connects separate networks to act as one |
| Gateway | Connects networks using different protocols |
| Modem | Converts data for transmission across cable/DSL |
| Repeater | Amplifies signal to extend network range |
| Wireless Access Point | Provides wireless connectivity to wired network |
| NIC | Network Interface Card — connects device to network |
| Firewall | Monitors and controls network traffic |
| Proxy Server | Intermediary between client and internet |
| IDS | Detects suspicious network activity — alerts only |
| IPS | Detects AND blocks suspicious network activity |

### Hub vs Switch
| | Hub | Switch |
|-|-----|--------|
| Data sent to | All devices | Only intended device |
| Efficiency | Low | High |
| Uses | Almost none anymore | Standard in all networks |

### Router functions
- Manages traffic between different networks
- Allows multiple devices to share one internet connection
- Uses routing table to find most efficient path

---

## Networking Models

### OSI Model — 7 Layers
| Layer | Name | Function |
|-------|------|---------|
| 7 | Application | User-facing protocols — HTTP, FTP, DNS |
| 6 | Presentation | Encryption, formatting |
| 5 | Session | Opens and manages sessions |
| 4 | Transport | TCP/UDP — reliable or fast delivery |
| 3 | Network | IP addressing and routing |
| 2 | Data Link | MAC addresses, frames |
| 1 | Physical | Cables, signals, raw bits |

### TCP/IP Model — 4 Layers
Practical implementation of OSI:
1. Application
2. Transport
3. Internet
4. Network Interface

---

## Networking Standards Organizations

| Organization | What they do |
|-------------|-------------|
| ISO | Created OSI model |
| ITU | Telecom standards |
| DARPA | Created TCP/IP |
| IEEE | 802 standards (WiFi, Ethernet) |
| W3C | Web standards |
| IETF | TCP/IP protocols and RFCs |

---

## Key Protocols & Port Numbers

### Web
| Protocol | Port | Purpose |
|----------|------|---------|
| HTTP | 80 | Standard web access |
| HTTPS | 443 | Encrypted web access |

### File Transfer
| Protocol | Port | Purpose |
|----------|------|---------|
| FTP | 21 | File transfer |
| SFTP | 22 | Secure file transfer |

### Remote Access
| Protocol | Port | Purpose |
|----------|------|---------|
| SSH | 22 | Secure remote control |
| Telnet | 23 | Remote control — no encryption |
| RDP | 3389 | Graphical remote desktop |

### Email
| Protocol | Port | Purpose |
|----------|------|---------|
| SMTP | 25 | Sending emails |
| POP3 | 110 | Download and delete emails |
| IMAP4 | 143 | Sync emails across devices |

### Network Management
| Protocol | Port | Purpose |
|----------|------|---------|
| DNS | 53 | Domain name to IP resolution |
| DHCP | 67, 68 | Automatic IP address assignment |
| SNMP | 161 | Network device monitoring |
| LDAP | 389 | Directory services, authentication |
| SMB | 137-139 | File and printer sharing |

---

## TCP vs UDP

| | TCP | UDP |
|-|-----|-----|
| Reliability | Guaranteed delivery | No guarantee |
| Speed | Slower | Faster |
| Error checking | Yes | No |
| Use case | FTP, web, email | Streaming, gaming, calls |

---

## Wireless Network Types

| Type | Range | Standard | Technology |
|------|-------|---------|-----------|
| WPAN | ~10m | IEEE 802.15 | Bluetooth, Zigbee |
| WLAN | Home/office | IEEE 802.11 | WiFi |
| WMAN | City-wide | IEEE 802.16 | WiMAX |
| WWAN | Regional/global | 4G, 5G, LoRaWAN | Cellular |
| WANET | Flexible | 802.20, 802.22 | Ad hoc, no infrastructure |

### Cellular Evolution
2G → 3G → 4G → 5G — each generation faster and more efficient

---

## Ports & Sockets
- Devices can have up to **65,536 ports**
- Each port linked to specific protocol and application
- **Socket** = IP address + protocol + port = enables two-way communication

---

## Key Takeaways
- Switch is smarter than hub — sends data only to intended device
- Router connects different networks using IP addresses
- OSI has 7 layers, TCP/IP has 4 — both describe same process
- Memorize key port numbers — comes up in every SOC interview
- HTTPS = port 443, SSH = port 22, DNS = port 53
- TCP = reliable, UDP = fast — pick based on use case
- IDS alerts only, IPS alerts AND blocks
- Telnet is insecure — always use SSH instead
