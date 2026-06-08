# Day 7 — Security Monitoring, Threat Hunting & Incident Response

**Date:** June 8, 2026
**Source:** Cybersecurity Fundamentals with Cisco Tools — Module 2 - Completed 

---

## Data Sources & Logs
Every device on a network generates logs — firewalls, servers,
endpoints, and applications.

| Log Type | What it records |
|----------|----------------|
| System Logs | Login attempts, system errors, user activities |
| Application Logs | Access or modification of data within software |
| Firewall Logs | Network traffic allowed or denied |
| IDS/IPS Logs | Exploit attempts and known attack signatures |
| Network Logs | Traffic data — detects DDoS, data exfiltration |

---

## Visibility in Security Monitoring
**Visibility** = monitoring all activities across networks and systems
to detect threats early.

### Benefits of Full Visibility
- Faster threat detection — real time identification before escalation
- Proactive security — find gaps before attackers do
- Improved incident response — quickly find root cause
- Regulatory compliance — meets reporting requirements

### Challenges
| Challenge | Why it's hard |
|-----------|--------------|
| Large data volume | Massive logs make finding threats difficult |
| Encrypted traffic | Tools can't inspect contents of encrypted data |
| Proxies | Attackers hide true IP behind proxy servers |
| SSL decryption | Inspecting encrypted traffic impacts performance and privacy |

---

## Data Correlation
Combining data from multiple sources to get full picture of an attack.

**Why it matters:**
- Detects sophisticated attacks invisible in a single log source
- Traces attacker's path across the network
- Understands full scope of incident for better response

---

## Encryption — Double-Edged Sword
- Protects sensitive data from unauthorized access ✅
- Prevents security tools from inspecting traffic contents ❌
- Malware can hide inside encrypted communications
- Data exfiltration attempts can go undetected

---

## Proxies in Attacks
- Attackers route traffic through proxy servers to hide true IP
- Complicates incident response — hard to trace origin
- Delays blocking of malicious activity

---

## Threat Hunting
Proactively searching for threats that evade automated detection.
Unlike SIEM alerts — threat hunters go looking, not waiting.

**Focus:** Advanced Persistent Threats (APTs)
- Stealthy attackers who stay hidden for long periods
- Traditional detection often misses them

### Tools for Threat Hunting
| Tool | Purpose |
|------|---------|
| Splunk | Log analysis and real-time monitoring |
| Wireshark | Captures and analyzes network packets |
| EDR tools | Visibility into endpoint activities and behavior |

### Best Practices
- Train hunters continuously — attack techniques evolve fast
- Use right tools — log analysis, network analyzers, EDR, SIEM
- Document every hunt — build central repository of findings
- Share findings with other teams to improve overall security posture

---

## Log Analysis in Incident Response
Examining log records to detect patterns, anomalies, and
suspicious activities.

**What logs help you do:**
- Identify root cause of incidents
- Trace attacker activities and exploited vulnerabilities
- Provide evidence for legal and compliance investigations

### Best Practices for Log Analysis
- Use centralized log management — correlate from multiple sources
- Establish baselines for normal activity — spot deviations
- Use automated tools with ML to detect anomalies
- Correlate data across log types for full attack picture
- Retain logs according to regulatory requirements

### Real World Case Studies
- **Capital One 2019** — log analysis detected misconfigured
  firewall exploited by attacker
- **Uber 2016** — highlighted need for rigorous log monitoring
  especially in cloud environments

---

## False Positives vs True Incidents

| | False Positive | True Incident |
|-|---------------|--------------|
| What it is | Benign activity flagged as malicious | Genuine security breach |
| Action needed | Tune detection rules | Immediate response |
| Risk | Wastes analyst time, alert fatigue | Real damage if ignored |

### Handling False Positives
- Initial triage — correlate logs, review past activity
- Fine-tune detection tools and alert thresholds
- Use ML and automation to reduce low-risk false alerts

### Alert Fatigue
Too many false positives → analysts start ignoring alerts →
real threats get missed. Fine-tuning rules is critical.

---

## Mitigation Strategies
Limit damage by containing threats before they spread.

**Immediate actions:**
- Isolate infected systems from network
- Block malicious IP addresses
- Disable compromised accounts temporarily

---

## Post-Incident Actions
After containment — learn and improve.

1. Conduct post-incident review
2. Analyze vulnerabilities exploited
3. Update security policies
4. Share lessons learned across teams
5. Restore systems from clean backups
6. Test restored systems before reconnecting
7. Monitor for reinfection
8. Improve patch management and access controls

---

## Key Takeaways
- Logs are the foundation of all security monitoring
- Full visibility requires data from all sources — not just one
- Encryption and proxies are the biggest monitoring challenges
- Threat hunters proactively look — they don't wait for alerts
- Log analysis is essential for both detection and investigation
- False positives cause alert fatigue — tune rules regularly
- Post-incident review is how security teams get better over time
