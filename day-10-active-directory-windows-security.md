# Day 10 — Active Directory, Windows Security & Kerberos

**Date:** June 11, 2026
**Source:** IBM Cybersecurity Analyst — Operating Systems: Overview,
Administration & Security (Module 2)
**Achievement:** - Module 2 Complete

---

## Active Directory (AD) Accounts

### Default Local Accounts
| Account | Purpose |
|---------|---------|
| Administrator | Full control over local system |
| Guest | Limited access, temporary use |
| KRBTGT | Kerberos authentication service account |
| HelpAssistant | Remote support sessions |

### Domain Admin Account
Most powerful account in an AD domain.

**What it can do:**
- Create and manage all user accounts
- Set and enforce security policies network-wide
- Install or upgrade software across multiple devices

**How to protect it:**
- Strong complex passwords, changed regularly
- Limit number of users with Domain Admin privileges
- Enable MFA
- Monitor and audit all Domain Admin activity
- Never use for everyday tasks — only when necessary
- Keep systems patched

---

## Windows Security Settings

### UAC (User Access Control)
Prevents unauthorized changes by prompting approval for admin actions.

| Prompt Type | Who sees it |
|-------------|------------|
| Consent prompt | Administrators — approve or deny |
| Credential prompt | Standard users — must enter admin credentials |

### Encryption Options

| Tool | What it encrypts | Best for |
|------|-----------------|----------|
| BitLocker | Entire drives — system and data | Protecting whole disk if stolen |
| BitLocker To Go | Removable storage — USB drives | Securing portable devices |
| EFS (Encrypting File System) | Individual files and folders on NTFS | Selective file encryption |

**EFS key point:** Integrates with Windows user accounts — only
the authorized user can decrypt their files automatically.

---

## User Management & Permissions

### NTFS vs Shared Permissions

| | NTFS Permissions | Shared Permissions |
|-|-----------------|-------------------|
| Applies to | Individual files and folders | Shared folders over network |
| Granularity | High — Read, Write, Full Control, Modify | Lower — Read, Change, Full Control |
| Location | Local NTFS drive | Network shares only |

### Secure Group Structure Design
- **Role-based groups** — HR, Finance, IT separate groups
- **Least privilege** — minimum permissions per group
- **Hierarchical grouping** — nested groups for complex orgs
- **Separation of duties** — critical tasks need multiple approvals
- **Centralized management** — Active Directory for control and auditing
- **Regular review** — audit memberships and remove unnecessary access

---

## Windows Security Tools

### Microsoft Defender Antivirus
- Built-in for Windows 10 and 11
- Real-time protection against viruses, malware, spyware
- Uses cloud-based threat detection
- Auto-updates virus definitions
- Don't run multiple antivirus programs simultaneously — causes conflicts

### Windows Firewall
- Monitors and controls incoming/outgoing network traffic
- Rules can be predefined or custom
- Allows exceptions for necessary network access
- Sends notifications when connections are blocked

---

## Patching & Updates

### Patches vs Updates
| | Patch | Update |
|-|-------|--------|
| Purpose | Fixes bugs and security vulnerabilities | Patches + new features + performance |
| Priority | Critical patches = apply immediately | Schedule regularly |

### Patch Management Process
1. Identify vulnerable systems
2. Acquire the patch
3. Test before deployment
4. Install and verify
5. Document and monitor

### Best Practices
- Apply critical security patches immediately
- Test patches before wide deployment
- Use automated patch management tools
- Have rollback/contingency plans
- Create system restore points before installing

### Microsoft Update & WSUS
- **Microsoft Update** — web service for Windows, Office, drivers
- **Automatic updates** — downloads and installs on schedule
- **WSUS (Windows Server Update Services)** — admins control and
  automate update distribution across corporate network
- WSUS allows testing and staged deployment to minimize disruption

---

## Kerberos Authentication

**What it is:** Secure authentication protocol developed by MIT.
Uses cryptography and a trusted third party to verify identities
over insecure networks. Primary protocol in Windows Active Directory.

### Key Components
| Component | Role |
|-----------|------|
| Client | User requesting access |
| Authentication Server (AS) | Validates credentials, issues TGT |
| Ticket Granting Server (TGS) | Issues service tickets |
| Key Distribution Center (KDC) | Combines AS + TGS |
| Hosting Server | The service the client wants to access |

### Kerberos Flow
1. Client requests **TGT** (Ticket Granting Ticket) from AS
2. AS validates credentials → issues encrypted TGT
3. Client uses TGT to request **service ticket** from TGS
4. TGS verifies TGT → issues service ticket for target server
5. Client presents service ticket to server → access granted
6. **Mutual authentication** — both client and server verify each other

### Benefits
- Enables **SSO** — log in once, access multiple resources
- Mutual authentication — both sides verify identity
- Renewable session tickets — reduces server overhead
- Supports interoperability across different networks

---

## Windows Auditing

**Security auditing** = tracking specific events in Windows OS to
monitor activity and detect security breaches.

### Key Audit Policies
| Policy | What it monitors |
|--------|-----------------|
| Account Logon Events | Login attempts and authentication |
| Account Management | User account changes |
| Directory Service Access | AD object access |
| Logon Events | Local and network logons |
| Object Access | File, folder, registry access |
| Policy Changes | Security policy modifications |
| Privilege Use | Use of elevated privileges |
| Process Tracking | Program execution |
| System Events | Startup, shutdown, system changes |

### Creating Effective Audit Policies
1. Identify critical assets to monitor
2. Determine relevant events and actions
3. Develop structured audit policy
4. Implement via system settings
5. Regularly review audit logs
6. Update policy as threats evolve

---

## Key Takeaways
- Domain Admin is the most powerful AD account — protect it heavily
- UAC prevents unauthorized privilege escalation
- BitLocker encrypts drives, EFS encrypts individual files
- NTFS permissions are more granular than shared permissions
- Always apply principle of least privilege to user groups
- Critical patches must be applied immediately — no delays
- WSUS gives admins control over enterprise update deployment
- Kerberos = TGT → Service Ticket → Access — remember the flow
- Auditing is how you detect unauthorized activity after the fact
- Windows audit logs are what SOC analysts read daily
