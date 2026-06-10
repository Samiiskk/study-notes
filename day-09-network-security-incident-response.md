# Day 9 — Network Security, Attack Patterns & Incident Response

**Date:** June 10, 2026
**Source:** Cybersecurity Fundamentals with Cisco Tools — Module 3
**Achievement:** ✅ Module 3 Complete — Cisco cert module done

---

## IDS vs IPS vs Firewall

| Tool | Role | Action |
|------|------|--------|
| IDS | Monitors traffic, detects threats | Alerts only — passive |
| IPS | Monitors traffic, blocks threats | Drops packets, resets connections — active |
| Firewall | Controls traffic based on rules | Allows or blocks based on policy |

### How to Deploy All Three Together
- **IDS** — inside network to catch threats that bypass perimeter
- **IPS** — at network entry points to block before reaching critical systems
- **Firewall** — at network boundaries to enforce access control and segment network

### Best Practices
- Regularly update signature databases
- Customize detection rules for your environment
- Implement network segmentation
- Monitor alerts in real time
- Conduct regular audits and tuning

---

## Network Traffic Analysis

**What it involves:**
- Capturing and inspecting data packets across the network
- Examining headers — source/destination IPs, ports
- Flow analysis — data transfer rates, connection durations

**What to look for:**
- Data exfiltration attempts
- DDoS attack patterns
- Malware command and control communication
- DNS tunneling

### Key Tools
| Tool | Type | Purpose |
|------|------|---------|
| Wireshark | GUI | Capture and analyze packets visually |
| TCPdump | CLI | Command-line packet capture |

### Using Wireshark to Detect Exfiltration
- Filter for unusual outbound connections
- Look for large volumes of data sent externally
- Identify abnormal HTTP requests
- Spot traffic spikes deviating from baseline

### DNS in Attacks
- DNS translates domain names to IPs — essential for internet
- Attackers abuse DNS for:
  - **DNS tunneling** — hide data in DNS queries
  - **Command and control** — communicate with malware

---

## Network Security Assessment Tools

| Tool | Purpose | Type |
|------|---------|------|
| Nmap | Network discovery, open ports, services | Open source |
| Nessus | Vulnerability scanning, missing patches, reports | Proprietary |
| OpenVAS | Vulnerability scanning — free alternative to Nessus | Open source |
| Wireshark | Packet capture and traffic analysis | Open source |

### Limitations of Assessment Tools
- Generate false positives
- Time consuming on large networks
- Only detect known vulnerabilities — miss zero-days

### Best Practices
- Schedule regular scans
- Prioritize vulnerabilities by severity
- Validate findings with penetration testing
- Regularly review network configurations

---

## Common Network Attack Patterns

| Attack | How it works | Defense |
|--------|-------------|---------|
| DDoS | Botnet floods target with traffic | Rate limiting, cloud DDoS protection, WAF |
| MITM | Intercepts and alters communications | HTTPS/TLS encryption, VPN |
| SQL Injection | Malicious SQL queries manipulate database | Input validation, parameterized queries |
| Phishing | Tricks users into revealing credentials | User training, email filtering |

### Rate Limiting vs DDoS
- Set thresholds — max requests per IP per time window
- Block or delay traffic exceeding the limit
- Configure on web servers, load balancers, or firewalls

---

## Security Policies
Formal documents defining how an organization protects digital assets.

### Essential Policy Types
| Policy | What it covers |
|--------|---------------|
| Access Control | Least privilege, role-based access, regular reviews |
| Data Protection | Encryption in transit and at rest |
| Incident Response | Reporting procedures, response steps |
| Acceptable Use | What employees can and cannot do |

### Best Practices
- Involve IT, legal, HR, and leadership in policy creation
- Align with regulations — GDPR, HIPAA
- Keep policies clear and actionable
- Review and update regularly as threats evolve
- Enforce consistently — policies only work if followed

---

## Incident Response Plan (IRP) vs Disaster Recovery Plan (DRP)

| | IRP | DRP |
|-|-----|-----|
| Focus | Security breaches | Catastrophic events including natural disasters |
| Goal | Contain, minimize, restore | Business continuity and full recovery |
| Scope | Security incidents | Broader — ransomware, disasters, outages |

### IRP Phases
1. Preparation
2. Identification
3. Containment
4. Eradication
5. Recovery
6. Lessons Learned

### DRP Key Components
- Backup and restoration procedures
- Failover mechanisms
- Communication plans
- Regular testing and updates

**Case study:** 2021 Colonial Pipeline ransomware attack showed the
critical importance of coordinated IRP and DRP.

---

## Continuous Monitoring
Real-time data collection and analysis to identify threats early.

### What Gets Monitored
- Network traffic
- System performance
- User activity and behavior

### Benefits
- Early threat detection before significant damage
- Real-time alerts and investigation
- Regulatory compliance support

### Best Practices
- Integrate with SIEM to centralize and correlate data
- Establish baselines for normal activity
- Use ML-based automated threat detection
- Focus on critical systems and high-value assets
- Regularly adjust monitoring policies

### Main Challenge
Data overload — requires good filtering and automation to focus
on actionable threats only.

---

## Security Training & Awareness
Employees are the first and last line of defense.

### Key Training Areas
- Phishing and social engineering recognition
- Password management and MFA usage
- Data classification and handling
- Incident reporting procedures

### Best Practices
- Regular role-tailored training sessions
- Leadership involvement improves engagement
- Run phishing simulations to test readiness
- Incentivize good security behavior

**Case study:** Financial institution reduced phishing incidents
significantly after comprehensive training and simulations.

---

## Key Takeaways
- IDS detects, IPS detects and blocks, Firewall controls access
- Deploy all three together for layered network defense
- Wireshark and Nmap are essential tools for every SOC analyst
- DNS can be weaponized — monitor DNS traffic for tunneling
- Rate limiting is a simple but effective DDoS defense
- IRP handles breaches, DRP handles disasters — both are needed
- Continuous monitoring + SIEM = real time threat visibility
- Security training reduces human error — the biggest attack vector
