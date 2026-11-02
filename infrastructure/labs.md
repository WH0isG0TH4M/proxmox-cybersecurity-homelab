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
| 107 | AD-Heaven | VM | Domain User 1 |
| 108 | AD-SPIDEY | VM | Domain User 2 |
| 101 | Pi-hole | LXC | DNS filtering and ad blocking |
| 102 | Jellyfin | LXC | Media server |
| 106 | Ollama | LXC | Local AI inference |

## 1. Active Directory Lab

### Systems

| VMID | Name | Role |
|---|---|---|
| 104 | AD | Domain Controller |
| 107 | AD-Heaven | Domain User 1 |
| 108 | AD-SPIDEY | Domain User 2 |

### Purpose

A virtualized Windows domain environment for practicing Active Directory administration, attack techniques, and defensive security.

### Areas of Practice

- Domain Controller administration
- Active Directory enumeration
- Kerberos authentication attacks
- Password attacks
- Domain privilege escalation
- Group Policy security
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
