# Proxmox Cybersecurity Homelab

**Virtualization | Active Directory | Malware Analysis | Network Security | Self-Hosted Services**

A personal cybersecurity homelab built on Proxmox VE, designed for hands-on security research, infrastructure management, virtualization, and experimentation.

## Overview

This homelab serves as a dedicated environment for learning and experimenting with different areas of cybersecurity and system administration.

It combines virtual machines, Linux containers, isolated lab environments, and self-hosted services into a centralized virtualization platform.

## Hardware Specifications

| Component | Specification |
|---|---|
| Device | Dell OptiPlex 3050 Micro |
| Processor | Intel Core i5-7500 |
| Memory | 16 GB RAM |
| Storage | 512 GB SSD |
| Hypervisor | Proxmox VE 9.2.2 |

## Virtualization Infrastructure

The environment consists of the following virtual machines and Linux containers.

| VMID | Name | Type | Purpose |
|---|---|---|---|
| 100 | FLARE-VM | VM | Windows malware analysis |
| 101 | Pi-hole | LXC | DNS filtering and ad blocking |
| 102 | Jellyfin | LXC | Self-hosted media server |
| 104 | AD | VM | Active Directory environment |
| 105 | REMnux | VM | Linux malware analysis |
| 106 | Ollama | LXC | Local AI model deployment |
| 107 | AD-Heaven | VM | Active Directory lab |
| 108 | AD-SPIDEY | VM | Active Directory lab |

## Core Technologies

- Proxmox VE
- KVM Virtualization
- Linux Containers (LXC)
- Windows Server / Active Directory
- FLARE-VM
- REMnux
- Pi-hole
- Jellyfin
- Ollama

## Key Areas

### Cybersecurity Research
- Active Directory enumeration and security assessment
- Windows privilege escalation
- Malware analysis and reverse engineering
- Network reconnaissance
- Vulnerability assessment

### Infrastructure Management
- Virtual machine management
- Linux container management
- Virtual networking
- Storage management
- Network isolation

### Self-Hosted Services
- DNS filtering with Pi-hole
- Media streaming with Jellyfin
- Local AI inference with Ollama

## Architecture

The homelab uses two virtual network bridges:

- `vmbr0` – Main LAN network.
- `vmbr1` – Isolated malware analysis network.

For the complete infrastructure design, network topology, and component breakdown, see:

## Repository Structure

```text
proxmox-cybersecurity-homelab/
├── README.md
├── docs/
├── infrastructure/
├── labs/
└── screenshots/
```

## Disclaimer

This environment is intended for educational purposes, authorized security testing, and personal research. All offensive security activities are performed within controlled lab environments.

---

**Maintained as a personal cybersecurity and infrastructure engineering project.**
