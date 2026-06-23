# Day 17 — Network Protocols, DNS, DHCP & Network Analysis

**Date:** June 23, 2026
**Source:** Network Security & Database Vulnerabilities (Module 3 continued)

---

## TCP vs UDP (Transport Layer)

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Connection-oriented | Connectionless |
| Reliability | Guaranteed delivery | No guarantee |
| Speed | Slower (error checking) | Faster |
| Use case | Files, web, email | Streaming, gaming, calls |
| Header | Includes sequence/ack numbers | Simple source/dest ports |

### TCP Three-Way Handshake
1. **SYN** — client sends synchronize request
2. **SYN-ACK** — server responds with ack
3. **ACK** — client confirms connection

### UDP Real-World Applications
- TFTP (port 69) — file transfer
- DNS (port 53)
- SNMP (161, 162)
- DHCP (port 67)
- VoIP (port 5060)
- IPTV (ports 80, 5004, 12000)

---

## DNS (Domain Name System)

**Purpose:** Translates human-readable domains → IP addresses

**Process:**
1. User enters google.com
2. DNS query sent to DNS server
3. Server responds with IP address
4. Device connects to that IP

**Security:** DNS filtering blocks access to malicious/unwanted sites.

---

## DHCP (Dynamic Host Configuration Protocol)

**Purpose:** Automatically assigns IP addresses to devices.

### DHCP Four-Step Handshake
1. **Discover** — client broadcasts looking for DHCP server
2. **Offer** — server responds with IP offer
3. **Request** — client requests the offered IP
4. **Acknowledge** — server confirms assignment

**Benefits:**
- No manual IP configuration
- Automatic IP lease management
- Scalable across networks

---

## Syslog Protocol

**Purpose:** Standardized message logging for network devices.

### Syslog Layers
| Layer | Function |
|-------|----------|
| Content | Stores messages |
| Application | Generates, interprets, routes, stores messages |
| Transport | Transports messages across network |

### Message Components
- **Facility code** — indicates software type (kernel, mail, etc.)
- **Severity level** — 0 (emergency) to 7 (debug)
- **Process ID** — which process generated message
- **Timestamp** — when event occurred
- **Hostname/IP** — which device reported event

**Key players:**
- Originator (event source)
- Collector (Syslog server)
- Relay server
- Transport sender/receiver

---

## Network Flows & Analysis

**NetFlow:** Data and statistics on packets traversing network interfaces.

### NetFlow Data Includes
- Packet counts and byte counts
- Timestamps
- Port usage
- Interface identities
- QoS information
- Protocol types (ICMP, UDP, TCP)
- Source/destination IP addresses and ports

**Use case:** Identify which protocols dominate traffic, track data ingress/egress.

---

## Port Mirroring & Promiscuous Mode

### Port Mirroring (SPAN)
- Configure switch to copy all traffic from one port to another
- Cisco calls it SPAN (Switch Port Analyzer)
- RSPAN (Remote SPAN) sends to different switch
- **Security risk:** Attackers with switch access can redirect traffic
- **Mitigation:** Send mirrored traffic to IDS for analysis

### Promiscuous Mode
- Network Interface Card (NIC) captures ALL frames
- Even frames not addressed to it
- Required for network analysis tools like Wireshark

---

## User Behavior Analysis (UBA)

**Purpose:** Monitor user actions to detect threats.

### Key Concepts
- **Baselining** — establish normal user behavior
- **Anomaly detection** — flag deviations from baseline
- **Contextual awareness** — consider user role and circumstances

### Techniques
- Machine learning — learns behavior patterns
- Statistical analysis — quantifies deviations
- Log analysis — examines multiple sources

### Use Cases
- Detect insider threats
- Identify compromised accounts
- Detect data exfiltration
- Track privilege abuse

### Challenges
- Privacy concerns
- False positives
- Scalability across large organizations

---

## Key Takeaways
- TCP = reliable but slower, UDP = faster but unreliable
- DNS translates domains to IPs — critical for web access
- DHCP automates IP assignment with 4-step handshake
- Syslog standardizes log messages across network
- NetFlow provides protocol and traffic statistics
- Port mirroring sends copies to IDS for analysis
- UBA detects user anomalies using ML and baselines
- Promiscuous mode needed for full packet capture
