# Dynamic Host Configuration Protocol (DHCP)

## Objective

Deploy and configure the DHCP Server role on the Windows Server 2025 Domain Controller to automatically assign IPv4 addresses and DNS settings to domain-joined client systems. Integrating DHCP with Active Directory and DNS enables centralized network configuration while reducing manual administration.

---

## Environment

| Component | Value |
|-----------|-------|
| Server | DC01 |
| Client | WIN11-01 |
| Domain | vigtech.local |
| Server IP | 192.168.10.10 |
| DHCP Scope | Corporate LAN |
| Address Pool | 192.168.10.100 – 192.168.10.200 |
| Subnet Mask | 255.255.255.0 |

---

# DHCP Role Installation

The DHCP Server role was installed using the **Add Roles and Features Wizard** in Server Manager. Following installation, the DHCP server was authorized within Active Directory to begin leasing IP addresses.

## Add Roles Wizard

![](Screenshots/images/dhcp/01-add-roles-wizard.png)

## DHCP Role Selection

![](Screenshots/images/dhcp/02-dhcp-role-selection.png)

## Installation Complete

![](Screenshots/images/dhcp/03-dhcp-installation-complete.png)

## DHCP Authorization

![](Screenshots/images/dhcp/04-dhcp-authorization.png)

## DHCP Manager

![](Screenshots/images/dhcp/05-dhcp-manager.png)

---

# DHCP Scope Configuration

A new IPv4 scope named **Corporate LAN** was created to provide IP addresses for client workstations.

| Setting | Value |
|----------|-------|
| Scope Name | Corporate LAN |
| Start Address | 192.168.10.100 |
| End Address | 192.168.10.200 |
| Lease Duration | 8 Days |
| Default Gateway | None (Host-Only Lab) |
| Preferred DNS Server | 192.168.10.10 |
| DNS Domain | vigtech.local |

## Scope Creation

![](Screenshots/images/dhcp/06-dhcp-scope-created.png)

## Scope Options

![](Screenshots/images/dhcp/07-dhcp-scope-options.png)

## Active Scope

![](Screenshots/images/dhcp/08-dhcp-scope-active.png)

---

# Client Validation

The Windows 11 workstation (**WIN11-01**) was reconfigured to obtain its IP address and DNS server automatically from DHCP.

After renewing the network configuration, the client successfully received:

- IPv4 Address: **192.168.10.100**
- DHCP Server: **192.168.10.10**
- DNS Server: **192.168.10.10**
- DNS Suffix: **vigtech.local**

This confirms that DHCP is successfully distributing network configuration to domain-joined clients.

## DHCP Client Lease

![](Screenshots/images/dhcp/09-dhcp-client-release.png)

---

# Address Lease Verification

The DHCP console confirmed that WIN11-01 successfully received a lease from the configured scope.

## Address Leases

![](Screenshots/images/dhcp/10-address-leases.png)

---

# Enterprise Relevance

DHCP is a core enterprise network service that centralizes IP address management and reduces manual configuration. Combined with Active Directory-integrated DNS, it allows client systems to automatically receive the correct network settings required for authentication, name resolution, and access to domain resources.

---

# Skills Demonstrated

- Windows Server Administration
- DHCP Server Deployment
- Active Directory DHCP Authorization
- IPv4 Scope Configuration
- DNS Integration
- Enterprise Network Services
- Windows 11 Domain Administration
- Client Network Validation
- Dynamic IP Address Management
- Infrastructure Troubleshooting

---

# Outcome

A fully functional DHCP infrastructure was deployed and integrated with Active Directory and DNS. Domain-joined Windows clients now automatically receive valid IP addresses and DNS settings from the Windows Server 2025 Domain Controller, completing the core network infrastructure required for the enterprise lab.
