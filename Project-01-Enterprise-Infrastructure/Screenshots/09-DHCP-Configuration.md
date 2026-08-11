# Dynamic Host Configuration Protocol (DHCP)

## Objective

Configure the DHCP Server role on the Windows Server 2025 Domain Controller to automatically assign IPv4 addresses and DNS settings to domain-joined client computers. This eliminates the need for manual IP configuration while ensuring clients can locate Active Directory services through the domain's DNS server.

---

## Environment

| Component | Value |
|-----------|-------|
| Server | DC01 |
| Client | WIN11-01 |
| Domain | vigtech.local |
| Server IP | 192.168.10.10 |
| DHCP Scope | Corporate LAN |
| DHCP Range | 192.168.10.100 - 192.168.10.200 |
| Subnet Mask | 255.255.255.0 |

---

## Installing the DHCP Server Role

The DHCP Server role was installed through **Server Manager** using the **Add Roles and Features Wizard**. After installation, the server was authorized within Active Directory to allow it to lease IP addresses on the domain network.

### Screenshots

![Add Roles Wizard](Screenshots/images/dhcp/01-add-roles-wizard.png)

![DHCP Role Selection](Screenshots/images/dhcp/02-dhcp-role-selection.png)

![Installation Complete](Screenshots/images/dhcp/03-dhcp-installation-complete.png)

![DHCP Authorization](Screenshots/images/dhcp/04-dhcp-authorization.png)

![DHCP Manager](Screenshots/images/dhcp/05-dhcp-manager.png)

---

## Creating the DHCP Scope

A new IPv4 scope named **Corporate LAN** was created to distribute addresses to client devices.

### Scope Configuration

| Setting | Value |
|---------|-------|
| Scope Name | Corporate LAN |
| Start Address | 192.168.10.100 |
| End Address | 192.168.10.200 |
| Subnet Mask | 255.255.255.0 |
| Lease Duration | 8 Days |
| Router | None (Host-Only Lab) |
| DNS Server | 192.168.10.10 |
| Parent Domain | vigtech.local |

### Screenshot

![DHCP Scope](Screenshots/images/dhcp/06-dhcp-scope-created.png)

---

## DHCP Scope Options

The DHCP scope was configured to automatically provide clients with the correct DNS configuration.

Clients receive:

- DNS Server: 192.168.10.10
- DNS Domain: vigtech.local

This allows all domain-joined devices to locate Active Directory resources without requiring manual DNS configuration.

### Screenshot

![DHCP Scope Options](Screenshots/images/dhcp/07-dhcp-scope-options.png)

---

## Active Scope

After configuration, the scope was activated and became available for client devices.

### Screenshot

![Active Scope](Screenshots/images/dhcp/08-dhcp-scope-active.png)

---

## Client Validation

The Windows 11 workstation was reconfigured to obtain both its IP address and DNS server automatically.

After renewing the network lease, the workstation successfully received:

- IPv4 Address: **192.168.10.100**
- DHCP Server: **192.168.10.10**
- DNS Server: **192.168.10.10**
- DNS Suffix: **vigtech.local**

This confirms that the DHCP server is correctly assigning network configuration to client systems.

### Screenshot

![Client Lease](Screenshots/images/dhcp/09-dhcp-client-lease.png)

---

## Address Lease Verification

The DHCP Manager was used to verify that WIN11-01 successfully obtained a lease from the configured DHCP scope.

### Screenshot

![Address Lease](Screenshots/images/dhcp/10-address-leases.png)

---

## Enterprise Relevance

DHCP is a foundational infrastructure service within enterprise networks. Centralized IP address management reduces administrative overhead, minimizes configuration errors, and allows network settings to be updated without manually reconfiguring individual devices. Integrating DHCP with Active Directory and DNS enables clients to automatically receive the correct DNS server and domain configuration, ensuring seamless authentication and resource discovery across the environment.

---

## Skills Demonstrated

- Windows Server Administration
- DHCP Server Installation
- DHCP Authorization
- IPv4 Scope Configuration
- DNS Integration
- Dynamic IP Address Management
- Active Directory Integration
- Enterprise Network Services
- Client Connectivity Validation
- Windows 11 Administration

---

## Outcome

A fully functional DHCP infrastructure was successfully deployed and integrated with Active Directory and DNS. Domain-joined clients now automatically receive valid IP addressing information and DNS settings from the Windows Server 2025 Domain Controller, completing the core enterprise network infrastructure for the lab.
