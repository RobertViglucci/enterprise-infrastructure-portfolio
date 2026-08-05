# Project 1 – Enterprise Active Directory Environment

## Executive Summary

This project documents the design and deployment of a Windows-based Active Directory environment for a fictional company named Vig Technologies.

The goal is to simulate the responsibilities of an Infrastructure Engineer by designing, implementing, documenting, and maintaining an enterprise Windows environment using industry-standard technologies.

---
#Architecture

![Architecture](Architecture/EnterpriseEnvironment.drawio.svg)

---

## Business Scenario

Vig Technologies is a growing technology consulting company with approximately 50 employees.

The company currently has no centralized authentication, user management, or network services. As the Infrastructure Engineer, I have been tasked with designing and deploying a secure and scalable Active Directory environment to support company operations.

---

## Project Objectives

- Deploy Windows Server
- Configure Active Directory Domain Services
- Configure DNS
- Configure DHCP
- Join client computers to the domain
- Configure Organizational Units
- Configure Group Policy
- Deploy shared folders
- Document the complete deployment

---

## Technologies

- Windows Server
- Active Directory
- DNS
- DHCP
- Group Policy
- PowerShell
- VMware Workstation
- Windows 11
- Ubuntu Server

---

## Current Status

🟡 Planning

---

## Project Roadmap

### Phase 1 – Planning
- Design enterprise architecture
- Create network documentation
- Define IP addressing scheme

### Phase 2 – Windows Server Deployment
- Install Windows Server 2025
- Configure static IP
- Rename server to DC01

### Phase 3 – Active Directory
- Install AD DS
- Promote to Domain Controller
- Verify domain health

### Phase 4 – DNS & DHCP
- Configure DNS
- Configure DHCP scope
- Test client addressing

### Phase 5 – Client Deployment
- Install Windows 11
- Join to domain
- Test authentication

### Phase 6 – Group Policy
- Create OUs
- Create users/groups
- Apply Group Policies

### Phase 7 – Ubuntu Integration
- Deploy Ubuntu Server
- Configure SSH
- Prepare Docker environment
