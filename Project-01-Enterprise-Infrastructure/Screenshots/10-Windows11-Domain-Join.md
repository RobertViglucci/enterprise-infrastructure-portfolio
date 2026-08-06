# Windows 11 Domain Join

## Objective
Deploy a Windows 11 Enterprise workstation and join it to the `vigtech.local` Active Directory domain.

## Steps Performed

1. Installed Windows 11 Enterprise in VMware.
2. Renamed the workstation to `WIN11-01`.
3. Configured a static IPv4 address:
   - IP Address: 192.168.10.20
   - Subnet Mask: 255.255.255.0
   - DNS Server: 192.168.10.10
4. Verified connectivity to the domain controller using `ping`.
5. Verified DNS name resolution with `nslookup vigtech.local`.
6. Joined the workstation to the `vigtech.local` Active Directory domain.
7. Restarted the workstation.
8. Logged in successfully using a domain user account.

## Validation

- Successful ICMP communication with DC01.
- Successful DNS resolution for `vigtech.local`.
- Domain join completed successfully.
- Domain user profile created successfully.

## Screenshots

- 01-computer-rename.png
- 02-static-ip-configuration.png
- 03-domain-join-success.png
- 04-domain-user-login.png

## Lessons Learned

A Windows client requires correct DNS configuration pointing to the domain controller before it can locate and join an Active Directory domain. Static IP addressing and DNS validation simplified troubleshooting during deployment.
