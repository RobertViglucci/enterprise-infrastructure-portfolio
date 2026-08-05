# Vig Tech Network Design

## Overview

This document describes the initial enterprise network architecture for Vig Tech.

The environment is designed to support approximately 50 employees while remaining scalable for future growth.

---

## Infrastructure

### Virtual Machines

| VM | Role |
|----|------|
| Windows Server 2025 | Domain Controller |
| Windows 11 | Domain Client |
| Ubuntu Server | Linux Server |

---

## Network

Subnet:
192.168.10.0/24

Gateway:
192.168.10.1

Domain Controller:
192.168.10.10

Windows Client:
DHCP

Ubuntu:
DHCP

---

## Planned Services

- Active Directory
- DNS
- DHCP
- Group Policy
- File Services

---

## Future Expansion

- Microsoft Entra ID
- Azure
- VPN
- Monitoring
- Backup Server
