# Day 5 — Cisco Cybersecurity Fundamentals (Module 1)

**Date:** June 6, 2026
**Source:** Cybersecurity Fundamentals with Cisco Tools Specialization
**Status:** - Module 1 Complete

---

## CIA Triad
The three core principles of cybersecurity:

| Principle | Goal | Methods |
|-----------|------|---------|
| Confidentiality | Restrict data to authorized users only | Encryption, MFA |
| Integrity | Ensure data accuracy, prevent tampering | Hashing, digital signatures |
| Availability | Ensure authorized access when needed | Redundancy, load balancing |

---

## Defense in Depth
Multi-layered security — if one layer fails, others still protect.

| Layer | Example |
|-------|---------|
| Physical | Guards, CCTV, biometric access |
| Network | Firewalls, IDS/IPS |
| Endpoint | Antivirus, host-based firewalls |
| Encryption | Encrypting stored and transmitted data |
| Access Control | RBAC — only authorized personnel access sensitive data |

**Case study:** Equifax 2017 breach — failed patching + no network
segmentation led to massive data exposure.

---

## Firewalls

| Type | How it works |
|------|-------------|
| Packet Filtering | Inspects packets by IP/port — simple but limited |
| Stateful Inspection | Tracks active connections — detects sophisticated attacks |
| Next-Gen Firewall (NGFW) | Deep packet inspection + IPS + application monitoring |

**DMZ (Demilitarized Zone):** Area between public internet and internal
network containing public-facing servers. Firewalls isolate it to
prevent lateral movement if compromised.

---

## IDS vs IPS

| | IDS | IPS |
|-|-----|-----|
| Role | Detects and alerts | Detects and blocks |
| Type | Passive | Active |
| Action | Reports threats | Drops packets, blocks IPs |

### Detection Methods
- **Signature-based** — matches known threat patterns, struggles with zero-days
- **Anomaly-based** — detects unusual behavior vs baseline, can flag zero-days
  but may have false positives

### Types
- **NIDS** — monitors network-wide traffic
- **HIDS** — monitors specific host/device for file changes, unauthorized logins

---

## Endpoint Security

### Antivirus Detection Methods
- **Signature-based** — compares against known malware database
- **Heuristic analysis** — detects new malware by suspicious patterns
- **Behavioral analysis** — monitors real-time behavior for malicious activity

### EDR vs HIDS vs Antivirus
| Tool | What it does |
|------|-------------|
| EDR | Real-time monitoring, behavioral analysis, automated response, forensics |
| HIDS | Monitors host for file changes and unauthorized access |
| Antivirus | Detects and removes known threats via signatures |

Together they form a multilayered endpoint defense.

**EDR Tools:** Microsoft Defender, CrowdStrike Falcon, Carbon Black

---

## SIEM & Log Management

**SIEM** = Security Information Management + Security Event Management
- Collects and correlates logs from firewalls, servers, network devices
- Detects insider threats — unusual access patterns or data volumes
- Detects APTs — correlates indicators of compromise across sources
- Tracks lateral movement across the network

**Log Management:**
- Centralizes logs from all sources
- Ensures log retention for compliance
- Enables forensic analysis after incidents

---

## Cloud Security

### Service Models
- **IaaS** — virtualized compute resources (servers, storage)
- **PaaS** — platform for developing and managing applications
- **SaaS** — software delivered over internet on subscription

### Shared Responsibility Model
- **Cloud provider** — secures physical infrastructure
- **Customer** — secures data, applications, access controls

### 5 Best Practices
1. Encrypt data at rest, in transit, and in use
2. Apply principle of least privilege
3. Use security automation (Terraform, CloudFormation)
4. Perform regular security audits and penetration testing
5. Use CSPM tools to detect misconfigurations

---

## Attack Vectors & Vulnerabilities

**Attack vector** = path an attacker uses to gain access to a system

**Identifying vulnerabilities:**
- Vulnerability scanning — OpenVAS, Qualys
- Penetration testing — ethical hackers simulate attacks
- Code reviews and security audits

**Mitigation strategies:**
- Patch management — fix known vulnerabilities regularly
- Access control — limit access by role
- Security awareness training — phishing recognition
- Network segmentation — prevent lateral movement

---

## Threat Intelligence

| Type | Purpose |
|------|---------|
| Strategic | High-level threat landscape — used by executives |
| Tactical | Attacker techniques and procedures — used by security teams |
| Operational | Real-time active attack info — used by incident responders |

---

## Threat Hunting
Proactive search for threats that evade automated tools.
- Analyzes endpoint data and threat intelligence
- Identifies attack patterns before damage occurs
- Complements EDR and SIEM monitoring

---

## Key Legal Frameworks
| Law | What it covers |
|-----|---------------|
| GDPR | EU data protection — consent, minimization, right to delete |
| HIPAA | US health data — breach reporting, access controls |
| CFAA | US cybercrime law — prosecutes unauthorized computer access |

---

## Ethical Hacking
- Authorized testing to find vulnerabilities — legal and ethical
- Bug bounty programs — report vulnerabilities privately before exploitation
- Responsible disclosure — fix issues before going public

---

## Key Takeaways
- CIA Triad is the foundation of all cybersecurity decisions
- Defense in depth means no single point of failure
- IDS detects, IPS detects AND blocks
- SIEM is the central hub for log correlation and threat detection
- EDR + HIDS + Antivirus together = strong endpoint defense
- Cloud security is shared responsibility between provider and customer
- Threat intelligence has three levels — strategic, tactical, operational
