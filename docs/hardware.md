# Hardware Specifications

## Overview

The cybersecurity homelab runs on a Dell OptiPlex 3050 Micro using Proxmox VE as its hypervisor.

## Host Specifications

| Component | Specification |
|---|---|
| Manufacturer | Dell |
| Model | OptiPlex 3050 Micro |
| CPU | Intel Core i5-7500 |
| Memory | 16 GB DDR4 RAM |
| Storage | 512 GB SSD |
| Network | Gigabit Ethernet |
| Hypervisor | Proxmox VE 9.2.2 |

## Hardware Purpose

The physical host provides the computing resources for the following workloads:

- Active Directory lab environments
- Windows and Linux malware analysis
- Reverse engineering
- Local AI inference using Ollama
- DNS filtering using Pi-hole
- Media streaming using Jellyfin

## Resource Allocation

The host resources are shared among multiple virtual machines and containers.

| Resource | Total Capacity |
|---|---|
| CPU | Intel Core i5-7500 |
| RAM | 16 GB |
| Storage | 512 GB SSD |

Resource allocation may vary depending on the workload and running virtual machines.

## Maintenance and Monitoring

- Monitor CPU and memory utilization.
- Monitor storage capacity and disk health.
- Maintain regular VM and container backups.
- Use snapshots before major lab changes.
- Monitor Proxmox system updates.

## Limitations

The homelab operates on a compact system with limited memory and storage capacity. Running multiple resource-intensive virtual machines simultaneously may affect performance.
