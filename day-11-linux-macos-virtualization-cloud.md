# Day 11 — Linux, macOS, Virtualization & Cloud Computing

**Date:** June 12, 2026
**Source:** IBM Cybersecurity Analyst — Operating Systems: Overview,
Administration & Security (Modules 3 & 4)
**Achievement:** - Modules 3 & 4 Complete — Full course done!

---

## Linux Overview

### Why Organizations Use Linux
- Stable, secure, and efficient
- Open-source — free to use and modify
- Powers majority of web servers worldwide

### Popular Distributions
| Distro | Best for |
|--------|---------|
| Ubuntu | Beginner friendly, desktop and server |
| Debian | Stability focused |
| Red Hat/CentOS | Enterprise environments |
| Fedora | Cutting edge features |
| Linux Mint | Windows-like experience |

### GUI vs CLI in Linux
| | CLI | GUI |
|-|-----|-----|
| Control | Precise, powerful | Limited |
| Speed | Faster for complex tasks | Slower |
| Resources | Lightweight | More resource intensive |
| Learning curve | Steeper | Easier |

---

## Linux Terminal & Shell

### How Commands are Processed
1. User types command in terminal
2. Terminal sends to shell
3. Shell interprets and passes to kernel
4. Kernel translates to hardware instructions
5. Hardware executes operation
6. Results return through kernel → shell → terminal

### Shell Types
- **Bash** — default on most Linux systems
- sh, ksh, zsh, fish — alternatives

### Special Path Symbols
| Symbol | Meaning |
|--------|---------|
| `~` | Home directory |
| `/` | Root directory |
| `..` | Parent directory |
| `.` | Current directory |

---

## Essential Linux Commands

### Navigation & File Management
| Command | Purpose |
|---------|---------|
| `pwd` | Print working directory |
| `ls` | List files |
| `ls -l` | Detailed list |
| `ls -al` | Show hidden files too |
| `cd <dir>` | Change directory |
| `cd ..` | Go up one level |
| `mkdir` | Make new directory |
| `rmdir` | Remove directory |
| `cp` | Copy files |
| `mv` | Move or rename files |
| `rm` | Remove files |
| `touch` | Create empty file |
| `find` | Search for files |
| `chmod` | Change file permissions |

### File Content Commands
| Command | Purpose |
|---------|---------|
| `cat` | Display file contents |
| `more` | View file page by page |
| `head` | Show first lines of file |
| `tail` | Show last lines of file |
| `echo` | Print text to terminal |
| `grep` | Search text in files |
| `wc` | Count words/lines in file |

### System Information
| Command | Purpose |
|---------|---------|
| `whoami` | Show current user |
| `id` | Show user and group IDs |
| `uname` | Show system information |
| `ps` | Show running processes |
| `top` | Real-time process monitor |
| `df` | Show disk space usage |
| `date` | Show current date/time |

### Networking
| Command | Purpose |
|---------|---------|
| `hostname` | Show computer name |
| `ping` | Test connectivity |
| `ifconfig` | Show network interfaces |
| `curl` | Transfer data from URLs |
| `wget` | Download files from web |

### Compression
| Command | Purpose |
|---------|---------|
| `tar` | Archive files |
| `zip/unzip` | Compress/extract files |

---

## Linux Directory Structure

| Directory | Purpose |
|-----------|---------|
| `/` | Root — top level, everything branches from here |
| `/bin` | Essential commands for all users (ls, cp, mv) |
| `/sbin` | System admin commands for root user (ifconfig, reboot) |
| `/etc` | Configuration files for installed programs |
| `/var` | Variable data — system logs |
| `/tmp` | Temporary files — cleared on reboot |
| `/home` | User personal directories |
| `/boot` | Kernel and boot loader files — critical for startup |
| `/root` | Home directory for root user specifically |

**Key difference:**
- `/` = entire file system root
- `/root` = root user's personal home directory

---

## Linux Run Levels

| Level | Name | Description |
|-------|------|-------------|
| 0 | Halt | Stop all operations |
| 1 | Single-user | One user, maintenance mode |
| 2 | Multi-user no NFS | Multiple users, no network sharing |
| 3 | Full multi-user text | Full capabilities, no GUI |
| 4 | Undefined | Reserved for custom use |
| 5 | Full multi-user GUI | Normal desktop mode |
| 6 | Reboot | Restart system |

---

## Securing Linux

| Security Measure | Command/Action |
|-----------------|---------------|
| Update OS | `sudo apt update` then `sudo apt upgrade` |
| Remove unused software | `sudo apt-get remove program_name` |
| Remove with config files | `sudo apt-get purge program_name` |
| Enable firewall | UFW or iptables |
| Secure SSH | Disable root login, use SSH keys, enable 2FA |
| Monitor logs | Use syslog or centralized logging |
| Regular backups | Schedule with backup tools, store offsite |

---

## macOS Overview

### Key Features
| Feature | Purpose |
|---------|---------|
| FileVault | Full disk encryption |
| Keychain | Secure password storage |
| Time Machine | Automatic backup to external storage |
| Spotlight | Quick search and file finder |
| Mission Control | Manage all open windows |
| Terminal | CLI for advanced tasks |
| Disk Utility | Disk formatting and repairs |
| iCloud | Sync data across Apple devices |

### macOS File Types
- **.dmg** — disk image files
- **.pkg** — installer packages
- **.app** — application bundles

---

## Virtualization

**Definition:** Creating multiple virtual machines on one physical
computer using a hypervisor software layer.

### Benefits
- Efficient resource management
- Reduced hardware costs
- Faster deployment than physical hardware
- Redundancy — VMs can replace each other

### Hypervisor Types
| Type | How it works | Use case |
|------|-------------|---------|
| Type 1 (Bare Metal) | Runs directly on hardware | Enterprise servers, data centers |
| Type 2 | Runs on top of existing OS | Personal computers, labs |

**VMware = Type 2 hypervisor** — runs on your Windows 11

### Types of Virtualization
| Type | What it does |
|------|-------------|
| Desktop | Multiple desktop OSes on one machine |
| Network | Virtual network management via software |
| Storage | Multiple storage devices as one pool |
| Application | Run apps without installing them |
| Data Center | One physical data center acts as many |
| CPU | One CPU split into multiple virtual CPUs |

---

## Containers vs Virtual Machines

| | Containers | Virtual Machines |
|-|-----------|-----------------|
| Weight | Lightweight | Heavy |
| Startup | Almost instant | Minutes |
| Isolation | Process level | Full hardware level |
| Performance | Near native | Slightly reduced |
| OS | Shares host kernel | Own full OS |
| Use case | Microservices, apps | Full OS environments |

### Docker
- Open platform for building and running containers
- Uses Linux kernel namespaces for isolation
- Images are small, reusable, platform-independent
- Supports CI/CD and DevOps practices
- Not suitable for high performance or GUI-heavy apps

---

## Cloud Computing

### Service Models
| Model | What you manage | Example |
|-------|----------------|---------|
| IaaS | Apps, data, OS | AWS EC2 |
| PaaS | Apps and data only | Heroku |
| SaaS | Nothing — just use it | Gmail, Office 365 |
| Serverless | Just your code | AWS Lambda |

### Deployment Models
| Model | Description |
|-------|-------------|
| Public | Shared environment, accessible to many |
| Private | Dedicated to single organization |
| Hybrid | Combines public, private, and on-premises |

### Virtualization vs Cloud
| | Virtualization | Cloud Computing |
|-|---------------|----------------|
| Hardware dependency | High | Minimal |
| Access | Local network | Internet |
| Control | More control | Provider manages infrastructure |
| Use case | Server consolidation | Scalable on-demand resources |

---

## Mobile Devices

### iOS Key Points
- Favored for security and data privacy
- Setup requires Apple ID, Wi-Fi, SIM
- Settings app centralizes all device configuration
- About page shows IMEI, IP, MAC address, iOS version

### Android Key Points
- 77% global market share
- Open-source, supported by Google
- Setup requires Google account
- Monthly security updates
- Settings app manages all configurations
- Google Play Store for apps

---

## Key Takeaways
- Linux powers most servers — essential for SOC work
- `/etc` = configs, `/var` = logs, `/bin` = commands — memorize these
- Run level 3 = text multi-user, level 5 = GUI multi-user
- Always secure SSH — disable root login, use keys not passwords
- Type 1 hypervisor = bare metal, Type 2 = runs on OS (VMware)
- Containers are lighter and faster than VMs but less isolated
- Docker is the most popular container platform
- IaaS/PaaS/SaaS differ by how much you manage yourself
- SOC analysts work with Linux logs daily — know the directory structure
