# Day 8 — Endpoint Security & OS Hardening

**Date:** June 9, 2026
**Source:** Cybersecurity Fundamentals with Cisco Tools — Module 3
**Status:** - Module 3 in progress

---

## Antivirus & Anti-Malware

### Detection Methods
| Method | How it works | Limitation |
|--------|-------------|------------|
| Signature-based | Matches known malware signatures | Misses zero-days and new threats |
| Behavioral | Monitors suspicious program actions | Can generate false positives |

### What Behavioral Detection looks for
- Unauthorized modification of system files
- Unusual file encryption patterns
- Unauthorized access to sensitive system areas

### Best Practices
- Enable automatic signature updates
- Schedule regular full system scans
- Use centralized management to deploy updates across all systems
- Test updates in controlled environment before wide deployment
- Educate users on safe internet practices

### WannaCry Lesson
Updated antivirus + behavioral detection could have identified
WannaCry earlier — patching alone wasn't enough.

---

## HIDS vs HIPS

| | HIDS | HIPS |
|-|------|------|
| Full name | Host Intrusion Detection System | Host Intrusion Prevention System |
| Role | Detects and alerts | Detects and actively prevents |
| Action | Generates alerts only | Blocks processes, modifies firewall rules |
| Best for | Sensitive data environments | High security settings needing immediate response |

### How HIDS Works
- Continuously monitors logs and system processes
- Alerts administrators when anomalies detected
- Example: flagging abnormal login attempts in healthcare org

### How HIPS Works
- Enforces predefined rules to stop threats immediately
- Blocks unauthorized software installations in real time

### Limitations of Both
- Can generate false positives
- Require significant system resources
- Only monitor host level — need network tools too

---

## OS Hardening
Configuring security settings to reduce vulnerabilities and
minimize attack surface.

**Why it matters:** Default OS settings leave systems exposed.
Hardening closes those gaps before attackers find them.

### Windows Hardening
- Disable unneeded services like RDP if not required
- Use Group Policy for password and account security
- Enable automatic patch management
- Configure Windows Firewall properly

### Linux Hardening
- Apply principle of least privilege — restrict root access
- Disable unnecessary services — SSH if not needed
- Configure firewall using **iptables** or **UFW**
- Keep system updated using APT or Yum
- Enable logging with syslog
- Use **AIDE** for file integrity monitoring

### General Hardening Best Practices
- Disable unused services
- Apply security patches regularly
- Enforce strong authentication and MFA
- Apply least privilege to all accounts
- Enable logging and monitoring
- Use file integrity monitoring tools

---

## Application Whitelisting vs Blacklisting

| | Whitelisting | Blacklisting |
|-|-------------|-------------|
| Approach | Allow only approved apps | Block only known bad apps |
| Security level | High | Medium |
| Flexibility | Low — restrictive | High — more user freedom |
| Zero-day protection | Yes | No — reactive only |
| Complexity | High to maintain | Easier to implement |
| Best for | High security environments | Educational/creative environments |

### Best Practices
- Regularly update both lists as software and threats evolve
- Test whitelist changes in sandbox before full deployment
- Monitor blocked attempts in blacklisting for new threat patterns
- Combine both strategies with user education for best results

---

## Key Takeaways
- Signature-based detection misses zero-days — always combine with behavioral
- HIDS detects and alerts, HIPS detects and blocks
- Default OS settings are insecure — always harden after installation
- Whitelisting is more secure, blacklisting is more flexible
- Linux hardening = least privilege + disable SSH + UFW + patch regularly
- No single tool is enough — layer antivirus, HIDS/HIPS, and OS hardening
