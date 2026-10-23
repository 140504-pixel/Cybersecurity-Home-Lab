# Active Directory Domain Services (AD DS) Lab

## Objective
Deploy and configure a Windows Server 2022 domain controller to practice centralized identity and access management in a virtual lab.

## Lab Configuration

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Server OS | Windows Server 2022 |
| Domain Controller | CyberLab-DC01 |
| Domain | cyberlab.test |
| Network | NAT + Internal Network (intnet) |

Implementation

1. Domain Controller Setup
- Created a Windows Server 2022 virtual machine named `CyberLab-DC01`.
- Installed and configured Active Directory Domain Services (AD DS).
- Promoted the server to a domain controller for `cyberlab.test`.

2. Organizational Units
Created the following OUs using Active Directory Users and Computers:
- `IT-Department` — organizes IT user accounts.
- `Lab-Computers` — intended for domain-joined lab computers.

3. User and Group Management
- Created an Active Directory user: John Smith (`jsmith`).
- Created the security group `IT-Support`.
- Added `jsmith` to the `IT-Support` group.
- Practiced disabling, enabling, and resetting user accounts.

4. Group Policy
- Created the GPO `CyberLab - Auto Lock 5 Minutes`.
- Configured `Interactive logon: Machine inactivity limit` to `300` seconds.
- Linked the GPO to the `Lab-Computers` OU.
- Client-side verification completed successfully. The Windows 11 client joined the cyberlab.test domain, authenticated using the jsmith domain account, and successfully applied the CyberLab - Auto Lock 5 Minutes GPO. The policy was verified using gpresult, and the computer automatically locked after five minutes of inactivity.

Verification and Next Steps
- [x] Domain controller deployed
- [x] Active Directory domain configured
- [x] Organizational Units created
- [x] User and security group configured
- [x] Group Policy created and linked
- [x] Join Windows 11 client to domain
- [x] Verify domain user authentication
- [x] Verify Group Policy application

Lessons Learned
This lab provides practical experience with Active Directory administration, centralized account management, security groups, and Group Policy configuration. Further testing will verify client connectivity and policy enforcement.

Screenshots
Configuration screenshots will be added after review to ensure no passwords or sensitive information are exposed.

