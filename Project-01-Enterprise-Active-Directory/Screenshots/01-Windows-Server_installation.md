# Windows Server Installation

## Objective

Deploy Windows Server 2025 as the first domain controller for the Vig Tech environment.

## Environment

| Component | Value |
|-----------|-------|
| Hypervisor | VMware Workstation 17.5.x |
| Guest OS | Windows Server 2025 |
| Memory | 8 GB |
| CPU | 4 vCPUs |
| Disk | 80 GB |

## Installation Steps

### Screenshot 1 – VM Summary

![VM Summary](images/vm-summary.png)

**Explanation**

Created the DC01 virtual machine with 4 vCPUs, 8 GB of RAM, an 80 GB virtual disk, and NAT networking.

## Validation

- VM created successfully.
- Ready to begin Windows installation.

## Installation Summary

Windows Server 2025 was installed on a VMware Workstation virtual machine configured with 4 vCPUs, 8 GB of memory, an 80 GB virtual disk, and NAT networking. The installation used the Desktop Experience edition to provide a graphical interface, making it easier to configure and document Active Directory services during the initial stages of the project.

### Enterprise Consideration

Although many production environments use Server Core to reduce the attack surface and resource usage, Desktop Experience was selected for this lab to simplify administration and provide clear visual documentation of each configuration step.
