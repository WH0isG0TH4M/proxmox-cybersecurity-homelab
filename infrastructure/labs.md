# Homelab Infrastructure and Labs

## Overview

This document describes the virtualized cybersecurity environments running on my Proxmox homelab.

The labs are designed for Active Directory security testing, malware analysis, reverse engineering, and cybersecurity research.

## Lab Inventory

| VMID | Name | Type | Purpose |
|---|---|---|---|
| 100 | FLARE-VM | VM | Windows malware analysis |
| 104 | AD | VM | Active Directory Domain Controller |
| 105 | REMnux | VM | Linux malware analysis |
| 107 | AD-Heaven | VM | Windows 10 domain-joined workstation |
| 108 | AD-SPIDEY | VM | Windows 10 domain-joined workstation |
| 101 | Pi-hole | LXC | DNS filtering and ad blocking |
| 102 | Jellyfin | LXC | Media server |
| 106 | Ollama | LXC | Local AI inference |

## 1. Active Directory Lab

### Systems

| VMID | Proxmox Name | Windows Hostname | Role |
|---|---|---|---|
| 104 | AD | HYDRA-DC | Domain Controller |
| 107 | AD-Heaven | HEAVEN | Domain-joined workstation |
| 108 | AD-SPIDEY | PETER | Domain-joined workstation |

### Domain Information

| Component | Configuration |
|---|---|
| Domain | `MARVEL.LOCAL` |
| Domain Controller | `HYDRA-DC` |
| Server OS | Windows Server 2025 Standard Evaluation |
| Server Version | 24H2 |
| Server Build | 26100.32230 |
| Client OS | Windows 10 Pro 22H2 |

### Domain User Accounts

| Workstation | Domain User Account |
|---|---|
| AD-Heaven | `hdimla` |
| AD-SPIDEY | `pparker` |

### Purpose

A virtualized Windows domain environment based on the Active Directory lab from TCM Security's Practical Ethical Hacking (PEH) course.

It provides an environment for practicing Active Directory administration, attack techniques, enumeration, privilege escalation, and defensive security.

### Configured Components

- Active Directory Domain Services (AD DS)
- Active Directory Certificate Services (AD CS)
- Domain user and service accounts
- Service Principal Name (SPN) configuration
- SMB file sharing
- Group Policy Management

### Security Configurations

**SQLService Account**

A service account named `SQLService` is configured with a Service Principal Name (SPN).

This provides an environment for studying Kerberos authentication and Kerberoasting.

**SMB Share**

An SMB network share named `hackme` is configured for practicing SMB enumeration and access control testing.

**Group Policy**

A Group Policy Object (GPO) is configured to disable Windows Defender for controlled penetration testing exercises.

**Active Directory Certificate Services**

AD CS is installed to provide an environment for studying certificate-based authentication and potential certificate service misconfigurations.

### Areas of Practice

- Domain Controller administration
- Active Directory enumeration
- Kerberos authentication attacks
- Kerberoasting
- Password attacks
- SMB enumeration
- Group Policy enumeration
- AD CS security testing
- Domain privilege escalation
- BloodHound analysis
- Active Directory hardening
- Windows domain security assessment

## 2. Malware Analysis Lab

### Systems

| VMID | Name | Role |
|---|---|---|
| 100 | FLARE-VM | Windows malware analysis |
| 105 | REMnux | Linux malware analysis |

### Purpose

A dedicated environment for analyzing suspicious files, understanding malware behavior, and performing reverse engineering.

### Tools and Areas of Practice

- Ghidra
- IDA Pro
- x64dbg
- x32dbg
- cmder
- PEStudio
- DetectItEasy
- Process Monitor
- Wireshark
- FakeNet-NG
- FLOSS
- YARA
- Static analysis
- Dynamic analysis
- Reverse engineering

### Network Configuration

FLARE-VM and REMnux use two Proxmox network bridges depending on the activity.

| Bridge | Purpose |
|---|---|
| vmbr0 | Internet access for updates and downloading tools |
| vmbr1 | Isolated network for malware testing |

Both machines are manually switched between the two bridges.

During malware testing, FLARE-VM and REMnux are connected to `vmbr1`, allowing them to communicate with each other without normal internet connectivity.

### Security Considerations

Malware samples should only be analyzed in a properly isolated environment. Network access and communication between analysis systems must be controlled to prevent unintended exposure.

## 3. Local AI Environment

### System

| VMID | Name | Type | Purpose |
|---|---|---|---|
| 106 | Ollama | LXC | Local AI inference |

### Purpose

Ollama is used to run local language models for studying AI applications in cybersecurity, particularly AI-assisted hacking techniques and security research.

### Areas of Study

- AI-assisted security testing
- Understanding offensive security techniques
- Vulnerability research
- Security tool assistance
- Learning and analyzing attack methodologies
- Exploring local LLM capabilities in cybersecurity

## 4. Infrastructure Services

| VMID | Service | Type | Purpose |
|---|---|---|---|
| 101 | Pi-hole | LXC | DNS filtering and ad blocking |
| 102 | Jellyfin | LXC | Self-hosted media streaming |
| 106 | Ollama | LXC | Local AI inference |

## Lab Objectives

- Maintain separate environments for different cybersecurity activities.
- Practice offensive and defensive security techniques.
- Analyze malware in controlled environments.
- Experiment with Active Directory attack and defense.
- Explore local AI applications in cybersecurity.
- Improve virtualization and network management skills.

## Security Considerations

- Keep malware analysis environments isolated from trusted networks.
- Use VM snapshots before potentially destructive experiments.
- Restrict access to administrative interfaces.
- Avoid exposing lab services directly to the internet.
- Perform security testing only on systems where authorization has been granted.

## Future Documentation

- [ ] Document Active Directory domain topology
- [ ] Document domain users and permissions
- [ ] Document lab network assignments
- [ ] Document malware analysis workflow
- [ ] Document lab isolation and firewall rules
- [ ] Add screenshots of each lab
