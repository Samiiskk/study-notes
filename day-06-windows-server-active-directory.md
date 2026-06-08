# Day 6 — Windows Server, Active Directory & MMC

**Date:** June 7, 2026
**Source:** IBM Cybersecurity Analyst — Operating Systems Overview,
Administration & Security

---

## Windows Server Overview
Designed specifically for managing servers, networks, and business
environments.

### Key Features
| Feature | Purpose |
|---------|---------|
| Active Directory | Centralized authentication and policy enforcement |
| IIS | Web and application platform |
| Hyper-V | Virtualization |
| PowerShell | Automation and scripting |
| RDS | Remote Desktop Services |
| BitLocker | Full disk encryption |
| Storage Spaces Direct | Scalable storage |

### Network Services
| Service | Purpose |
|---------|---------|
| DNS | Translates domain names to IP addresses |
| DHCP | Automatically assigns IP addresses to devices |
| VPN | Secure remote access |
| RDS | Remote management and desktop access |

### Security & Access Control
| Feature | Purpose |
|---------|---------|
| Windows Firewall | Controls network traffic |
| AD RMS | Protects sensitive information |
| BitLocker | Full disk encryption |
| RBAC | Assigns permissions based on user roles |

---

## User Accounts in Windows
| Type | Description |
|------|-------------|
| Standard | Default account, limited privileges, everyday tasks |
| Administrator | Elevated privileges, system-wide changes |

### User Account Control (UAC)
- Prompts for permission when a process needs admin privileges
- Prevents unauthorized system changes
- Balances usability and security

**To run CMD as admin:**
1. Start menu → search Command Prompt
2. Right-click → Run as administrator
3. Click Yes on UAC prompt

---

## Key CMD Commands

### File & Directory Management
| Command | Purpose |
|---------|---------|
| dir | List files in directory |
| md | Make new directory |
| rd | Remove directory |
| ren | Rename file |
| del | Delete file |
| copy/xcopy/robocopy | Copy files and directories |
| cd / chdir | Navigate between directories |

### System Maintenance
| Command | Purpose |
|---------|---------|
| shutdown | Power management |
| sc | Manage system services |
| checkdisk | Check and fix disk errors |
| diskpart | Manage disk partitions |
| winver | Show Windows version info |

### Network Commands
| Command | Purpose |
|---------|---------|
| hostname | Show computer name |
| ipconfig | Show network configuration |
| ping | Test network connectivity |

### Group Policy Commands
| Command | Purpose |
|---------|---------|
| gpupdate | Force group policy update |
| gpresult | Show applied group policy results |

---

## Microsoft Management Console (MMC)
Customizable unified interface for Windows system administration.
Uses **snap-ins** — modular tools added to manage specific components.

### Key MMC Snap-ins
| Snap-in | Purpose |
|---------|---------|
| Computer Management | Disk partitions, device drivers, event logs, user accounts |
| Group Policy Management | User and computer settings across domain |
| Services & Task Scheduler | Manage services, automate tasks |
| Performance Monitor | Track system performance |
| Event Viewer | Analyze system events and errors |
| Device Manager | Manage hardware devices |
| Certificate Manager | Manage security certificates |
| Local Users and Groups | Manage local accounts |
| Disk Management | Manage disk configurations |

### Role-Based Administration in MMC
- Assign specific snap-ins only to authorized users
- Limit exposure of sensitive management tools
- Maintain compliance by distributing admin responsibilities

---

## Active Directory (AD)
Centralized management of user accounts, computers, and network
resources on a Windows network.

### AD Structure
| Level | What it is |
|-------|-----------|
| Domain | Basic unit — single administrative boundary |
| Tree | Multiple domains in parent-child hierarchy |
| Forest | Top level — multiple trees sharing common schema |

**Simple way to remember:**
Domains → form Trees → Trees → form a Forest

### Administrative Features
| Feature | Purpose |
|---------|---------|
| Organizational Units (OUs) | Containers to organize users/computers by department or location |
| Home Folders | Personal network storage for users |
| Folder Redirection | Redirects user folders to network for backup |
| Security Groups | Group users to simplify permission management |
| Group Policy Objects (GPOs) | Enforce network-wide settings and security policies |

### Why AD matters for SOC work
- Most enterprise environments run Active Directory
- Attackers frequently target AD to gain domain admin access
- SOC analysts monitor AD logs for suspicious logins and privilege escalation
- Kerberos authentication runs through AD

---

## Key Takeaways
- Windows Server is the backbone of most enterprise environments
- Active Directory = centralized control of users, computers, policies
- UAC prevents unauthorized privilege escalation
- MMC snap-ins allow role-based admin — reduce risk of excessive permissions
- Domain → Tree → Forest is AD's hierarchy
- As a SOC analyst you will see AD logs daily — know it well
