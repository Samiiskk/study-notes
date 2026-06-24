# Day 18 — Network Security: Inspection & Advanced Filtering

**Date:** June 24, 2026
**Source:** Network Security & Database Vulnerabilities - Completed 

---

## Stateless vs Stateful Inspection

### Stateless Inspection
- Examines EACH packet individually in isolation
- No memory of previous packets
- Uses Access Control Lists (ACLs)
- Checks source/destination IPs and ports
- **Faster** (no session tracking overhead)
- Good for: Protecting router resources, troubleshooting, QoS/CoS

**Example:** User opens web browser → router checks if source IP allowed + destination port permitted → packet forwarded (or dropped)

### Stateful Inspection
- Examines each packet **in context of its session**
- Maintains session database tracking:
  - Session ID
  - Policy name
  - Interfaces involved
  - IP addresses
  - Packet counts
  - NAT details
- Packets matching existing sessions take faster path
- New packets undergo stateless check → NAT → routing → zone → policy

**Comparison:**
| Feature | Stateless | Stateful |
|---------|-----------|----------|
| Session awareness | No | Yes |
| Performance | Faster | Slower |
| Security | Basic | Advanced |
| Context | No | Full session context |

---

## Firewall Types & Filtering

### Three Firewall Types
1. **Stateless firewalls** — filter packets individually (ACL-based)
2. **Stateful firewalls** — monitor connection states (more intelligent)
3. **Application-level firewalls** — inspect packet payloads for app-specific control

### Firewall Filters
- Enforce security policies on inbound/outbound traffic
- Combined with IDS/IPS for layered defense

---

## IDS vs IPS

### Intrusion Detection Systems (IDS)
- **Passively monitors** network traffic
- Compares against known attack signatures
- **Alerts** administrators when threats detected
- Does NOT block traffic

**Types:**
- **NIDS** (Network-based IDS) — monitors specific network segments
- **HIDS** (Host-based IDS) — monitors individual devices

**Advantages:**
- Provides detailed alerts + forensic data
- Minimal network performance impact

**Limitations:**
- Requires human intervention
- May generate false positives

### Intrusion Prevention Systems (IPS)
- **Actively blocks** threats in real-time
- Builds on IDS capabilities
- Takes immediate actions:
  - Drops malicious packets
  - Blocks suspicious IPs
  - Terminates connections

**Types:**
- **NIPS** (Network-based IPS)
- **HIPS** (Host-based IPS)

**Advantages:**
- Automated threat prevention
- Reduces analyst workload

**Disadvantages:**
- May impact network performance (inline inspection)
- Risk of blocking legitimate traffic if misconfigured

### Layered Defense
Firewalls block known threats → IDS monitors for anomalies → IPS actively stops malicious activities = robust defense.

---

## Network Address Translation (NAT)

**Purpose:** Modify IP address information in packet headers for security + efficient IP management.

### Three NAT Types

| Type | Mapping | Use Case |
|------|---------|----------|
| **Static NAT** | 1 private IP → 1 public IP | Devices needing external access (web servers) |
| **Dynamic NAT** | Private IPs from pool → public IPs as needed | Multiple devices needing internet without fixed public IPs |
| **PAT (overload)** | Multiple private IPs → 1 public IP (different ports) | Home/small networks |

### Benefits
- Masks internal IPs (security through obscurity)
- Conserves IPv4 addresses
- Simplifies network management

### Challenges
- Port forwarding misconfigurations
- IP address conflicts from overlapping ranges
- Performance overhead from address translation
- Complications with protocols embedding IP info (SIP/VoIP)

---

## File Integrity Monitoring (FIM)

**Purpose:** Continuously verify integrity of OS and application files against trusted baseline.

### FIM Process
1. **Establish baseline** — capture initial state of files
2. **Monitor for changes** — real-time or scheduled scans
3. **Alert on violations** — notify of unauthorized changes
4. **Respond** — investigate, restore, mitigate

### Files Monitored
- System files
- Configuration files
- Application files
- User data files

### Implementation
- Define monitoring scope
- Select hashing algorithm (MD5, SHA-256)
- Set monitoring frequency
- Detect changes
- Investigate violations

### Role in Security
- Identifies security breaches, malware, insider threats
- Complements firewalls + antivirus
- Supports compliance (PCI DSS, HIPAA, SOX)

---

## Data Loss Prevention (DLP)

**Purpose:** Protect sensitive information from unauthorized access + breaches.

### Core Functions
1. **Classify data** by sensitivity (personal, financial, proprietary)
2. **Tag information** with sensitivity labels
3. **Define policies** with access controls
4. **Enforce controls** on data in use, in motion, at rest

### DLP Technologies
- Content inspection
- User behavior analysis
- Encryption
- Tokenization

### Implementation Steps
1. Assess data security needs
2. Deploy DLP tools within infrastructure
3. Define compliant policies
4. Train employees

### Incident Response
- Real-time detection of breaches
- Incident response procedures
- System isolation
- Investigation + corrective actions

### Compliance Support
- GDPR compliance
- HIPAA compliance
- PCI DSS compliance

---

## Network Access Control (NAC)

**Purpose:** Restrict network access to authorized users/devices + ensure compliance.

### NAC Components
1. **Authentication** — verify user/device identity (credentials + digital certs)
2. **Authorization** — role-based access control (RBAC)
3. **Compliance enforcement** — check security posture (antivirus updates, etc.)

### Implementation
- Evaluate infrastructure
- Configure components
- Create policies
- Test thoroughly

### NAC Actions
- Monitor access attempts
- Quarantine non-compliant devices
- Automate remediation

### Integration
- Complements firewalls, IDS, antivirus
- Meets regulatory standards
- Enhances overall network security

---

## Endpoint Detection & Response (EDR)

**Purpose:** Detect, investigate, respond to suspicious activities on endpoints.

### Key Components
- **Continuous data collection** — logs, processes, files, network, user behavior
- **Threat detection** — signature, heuristic, behavioral analysis + ML
- **Investigation** — root cause analysis + timeline reconstruction
- **Response** — isolate endpoints, terminate processes, patch

### Implementation
- Assess security needs
- Deploy agents
- Define policies
- Continuous monitoring

### Incident Response
- Identify unauthorized activities
- Contain damage
- Investigate causes
- Apply corrections

### Role in Security
- Complements firewalls + IDS
- Enhances data protection
- Supports regulatory compliance

---

## Extended Detection & Response (XDR)

**Purpose:** Advanced platform integrating multiple security tools for enhanced detection + response.

### What XDR Extends
- Traditional EDR + network traffic analysis + cloud security + email security
- Centralizes alerts + responses

### Key Capabilities
- **Aggregates data** from diverse sources
- **Correlates** using ML + AI
- **Detects** using signature + behavioral + threat intel
- **Responds** with automated actions:
  - Isolate compromised systems
  - Block malicious traffic

### Implementation
- Assess organizational needs
- Plan deployment
- Configure data collection
- Define security policies
- Continuous monitoring

### Benefits
- Comprehensive visibility
- Automated response
- Forensic analysis support
- Audit trails for compliance

---

## Layered Security Strategy
Network Perimeter:

├── Firewalls (block known threats)

├── IDS/IPS (monitor + prevent)

├── NAC (control access)

└── DLP (prevent data exfiltration)Endpoint Level:

├── EDR (detect + respond)

├── FIM (monitor file integrity)

└── Antivirus (basic threat prevention)Cross-Layer:

└── XDR (integrate everything)

---

## Key Takeaways
- Stateful inspection = context-aware, stateless = fast but basic
- Firewalls + IDS + IPS = layered defense
- NAT provides security + IP efficiency
- FIM catches unauthorized file changes early
- DLP protects sensitive data
- NAC ensures device compliance
- EDR provides endpoint visibility + response
- XDR integrates all tools for unified defense
