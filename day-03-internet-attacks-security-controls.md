# Day 3 — Internet Attacks, Security Controls & Incident Response

**Date:** June 4, 2026
**Source:** IBM Cybersecurity Analyst — Introduction to Cybersecurity
Tools & Cyberattacks (Module 3) - Completed 

---

## Network Mapping
- Process of visualizing a network's physical and logical connections
- Tools: **Nmap** (discovers devices, ports, OS) and **Wireshark** (captures packets)
- Used by defenders to detect anomalies and manage networks
- Used by attackers to find unguarded entry points and vulnerable systems

---

## Internet Attacks

### IP Spoofing
- Altering source IP address in packets to hide attacker's identity
- Used in DDoS attacks and man-in-the-middle attacks
- Makes defense harder — replies go to forged IPs, not real attacker

**Defenses:**
- **Ingress filtering** — blocks incoming packets with forged source IPs
- **Egress filtering** — prevents internal systems sending spoofed packets

### DoS & DDoS Attacks
| Type | How it works |
|------|-------------|
| Ninja attack | Single packet exploiting protocol flaw, crashes system instantly |
| Death by 1000 cuts | Many small attacks (e.g. SYN flood) drain resources gradually |
| DDoS | Botnet floods target from many sources simultaneously |

**Defenses:**
- Redundancy — no single point of failure
- Traffic pacing and filtering
- Hardening — remove unnecessary services, patch software, change defaults
- SIEM and XDR for continuous monitoring

### Injection Attacks
**SQL Injection** — tricks database into running unintended commands
- Breaks confidentiality, authentication, authorization, data integrity

**Cross-Site Scripting (XSS)** — embeds malicious scripts into web pages
- Executes on victim's browser, steals data or alters content
- Types: server-side and client-side (both have reflected and stored variants)

---

## Security Controls

### Three Types
| Type | What it is | Example |
|------|-----------|---------|
| Administrative | Policies, procedures, training | Data classification policy |
| Physical | Protects hardware and facilities | Biometric locks, CCTV |
| Technical | Hardware/software/firmware defenses | Firewalls, MFA, SIEM |

### Four Functions
| Function | Purpose | Example |
|----------|---------|---------|
| Preventive | Stop incidents before they happen | Firewalls, MFA |
| Detective | Identify unauthorized actions | SIEM, IDS, CCTV |
| Deterrent | Discourage violations | Warning banners, security guards |
| Corrective | Repair damage, prevent recurrence | IR plan, reissue access cards |

---

## System Security
- **Access controls** — passwords, MFA, biometrics, VPNs
- **Encryption** — encodes data so only authorized users can read it
- **Patching** — fixes vulnerabilities in software
- **Backups** — restore systems after attack or data loss
- **Antivirus** — detects and removes malware using signature databases

---

## Network Security Tools
| Tool | Purpose |
|------|---------|
| Firewall | Filters traffic at network perimeter |
| NAC | Manages user authentication and device risk |
| IDPS | Detects and responds to threats beyond firewall |
| VPN | Encrypts traffic, masks IP for remote access |
| Network Segmentation | Limits attacker movement between network zones |
| SIEM | Aggregates and analyzes security data in real time |
| SOAR | Automates security workflows and incident response |

---

## Application Security (Security by Design)
Integrate security into every phase of SDLC — not just at the end.

**Key secure coding practices:**
- Input validation — prevent SQL injection
- Error handling — avoid crashes exposing vulnerabilities
- Avoid hardcoded credentials
- Access control — restrict data to authorized users only
- Encryption — protect data in storage and transit
- Secure logging — track activity, protect logs from tampering

---

## Vulnerability Management
1. Define and categorize all scan targets
2. Maintain up-to-date asset inventory
3. Run regular automated scans (off-peak hours)
4. Prioritize remediation by threat severity

**Scanning tools:** Nessus (proprietary), OpenVAS (open source)

**Testing types:**
- **SAST** — Static Application Security Testing
- **DAST** — Dynamic Application Security Testing
- **IAST** — Interactive Application Security Testing

---

## Incident Response Lifecycle
1. **Preparation & Planning** — form IR team, define roles, plan communication
2. **Detection & Analysis** — use IDS/SIEM to identify incidents
3. **Containment, Eradication & Recovery** — limit damage, remove cause, restore systems
4. **Post-Incident Activities** — review event, update defenses, communicate with stakeholders

## Digital Forensics in IR
- Collects and analyzes digital evidence during an incident
- Helps attribute attacks and improve future defenses
- **Chain of custody** — strict documentation ensuring evidence integrity for legal use

---

## Key Takeaways
- Nmap and Wireshark are essential tools for both attackers and defenders
- IP spoofing makes DDoS attacks harder to trace and block
- Security controls must combine administrative, physical, and technical layers
- Security by design means building security in from day one of development
- Digital forensics and IR work together — forensics provides the evidence, IR uses it
