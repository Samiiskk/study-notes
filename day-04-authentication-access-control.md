# Day 4 — Authentication & Access Control (IAM)

**Date:** June 5, 2026
**Source:** IBM Cybersecurity Analyst — Introduction to Cybersecurity
Tools & Cyberattacks (Module 4)
**Achievement:** - Module 4 Complete — 3rd IBM cert module done

---

## Identity & Access Management (IAM)
Framework of policies and technologies ensuring only authorized
individuals can access resources.

### The Four A's of IAM
| A | What it means |
|---|--------------|
| Administration | Creating, updating, deleting user accounts (provisioning) |
| Authentication | Verifying who you are |
| Authorization | Determining what you're allowed to do |
| Audit | Reviewing all above processes for correctness |

---

## Authentication

### Authentication Protocols
Verify identity before granting access.
- **RADIUS** — common in enterprise and VPN networks
- **CHAP** — challenge-based verification
- **EAP** — flexible protocol used in wireless networks
- **Kerberos** — MIT-developed, uses Key Distribution Center (KDC)
  - Primary protocol in Microsoft Active Directory environments

### Authentication Servers
Intermediaries between users and resources.
- Receive credentials → verify against database → grant or deny access
- Examples: Active Directory, LDAP servers, RADIUS servers

### Authentication Methods
| Method | Description |
|--------|-------------|
| Password | Most common but vulnerable to brute force |
| OTP | One-time password, valid for single use only |
| Biometrics | Fingerprint, iris, facial, voice, vein recognition |
| Smart Cards | Store cryptographic keys, inserted into card reader |
| Security Tokens | Hardware/software generating unique codes at intervals |
| Mobile Push | Approval notification sent to registered device |

### Three Factors of Authentication
- **Something you know** — password, PIN
- **Something you have** — mobile device, token, smart card
- **Something you are** — biometrics

---

## Multifactor Authentication (MFA)
Combines two or more factors for stronger security.
Goal: passwordless, frictionless environment with strong protection.

---

## Single Sign-On (SSO)
Log in once → access multiple systems without separate logins.

**Benefits:**
- Reduces number of passwords to remember
- Each connected system has its own unique password stored securely
- Reduces help desk costs from password reset requests

**Risks:**
- Single point of failure — if SSO is compromised, all systems exposed

**Mitigations:**
- Add MFA to SSO login
- Strong password policies
- Regular monitoring and alerts
- Principle of least privilege

---

## Passkeys (FIDO Standard)
- Private key stored on your device, unlocked by biometrics
- Secrets never transmitted — reduces attack surface
- Time-bound and cannot be reused unlike passwords
- Synced across devices via encrypted cloud sessions
- More secure than passwords — not vulnerable to phishing or reuse

---

## Authorization — Access Control Models
| Model | How it works |
|-------|-------------|
| RBAC (Role-Based) | Access based on user's role in organization |
| RuBAC (Rule-Based) | Access based on rules/ACLs — e.g. firewall rules |
| MAC (Mandatory) | OS enforces access, users cannot change permissions — used in military/government |
| DAC (Discretionary) | Owner controls permissions — e.g. Linux/Windows file permissions |

---

## Access Control Methods
**Traditional:**
- Usernames and passwords
- Digital certificates
- Tokens
- SSH keys
- Smart cards

**Innovative:**
- Biometric systems
- Behavioral biometrics (typing patterns)
- Geolocation and time-based restrictions
- MFA
- SSO

---

## Physical Security Threats
| Threat | Description |
|--------|-------------|
| Unauthorized access | Entering restricted areas without permission |
| Theft | Stealing laptops or hard drives with sensitive data |
| Tailgating | Following authorized person into secure area |
| Dumpster diving | Retrieving sensitive info from discarded materials |
| Surveillance | Spying on operations using cameras or devices |
| Vandalism | Destroying infrastructure causing downtime |

## Physical Security Controls
**On-premises:**
- Smart locks, CCTV, fencing, security guards, mantrap doors

**Server rooms:**
- Biometric access, HVAC systems, rack locks, tamper sensors

**Device protection:**
- Cable locks, port locks, screen filters, hard disk encryption

**Environmental:**
- Climate control (temperature + humidity)
- ESD protection — anti-static mats, wristbands
- UPS backup power, water detection systems

**Cutting-edge:**
- Drone detection systems
- Robotic security guards
- AI-based anomaly detection systems

---

## Key Takeaways
- IAM = Administration + Authentication + Authorization + Audit
- Kerberos is the core protocol in Windows Active Directory
- MFA is one of the strongest defenses available
- SSO improves usability but must be combined with MFA
- Passkeys are the future — more secure than passwords
- Physical security is just as important as digital security
- MAC is used in government/military — most restrictive model
