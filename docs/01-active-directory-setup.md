# Active Directory Domain Services (AD DS) Lab

## Objective

Deploy and configure a Windows Server 2022 domain controller to practice centralized identity and access management, domain authentication, and Group Policy administration in a virtual lab environment.

## Lab Configuration

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Server OS | Windows Server 2022 |
| Domain Controller | CyberLab-DC01 |
| Client OS | Windows 11 Pro |
| Client Computer | CyberLab-PC01 |
| Domain | cyberlab.test |
| Domain Controller IP | 192.168.100.10 |
| Client IP | 192.168.100.20 |
| Network | NAT + Internal Network (intnet) |

## Implementation

### 1. Domain Controller Setup

- Created a Windows Server 2022 virtual machine named `CyberLab-DC01`.
- Installed and configured Active Directory Domain Services (AD DS).
- Promoted the server to a domain controller for `cyberlab.test`.
- Configured DNS services for Active Directory name resolution.

### 2. Organizational Units

Created the following OUs using Active Directory Users and Computers:

- `IT-Department` — organizes IT user accounts.
- `Lab-Computers` — organizes domain-joined lab computers.

### 3. User and Group Management

- Created an Active Directory user: John Smith (`jsmith`).
- Created the security group `IT-Support`.
- Added `jsmith` to the `IT-Support` group.
- Practiced disabling, enabling, and resetting user accounts.

### 4. Windows 11 Domain Join

- Installed Windows 11 Pro on `CyberLab-PC01`.
- Configured internal networking and DNS resolution.
- Successfully joined the client to the `cyberlab.test` domain.
- Verified the computer object in the `Lab-Computers` OU.
- Successfully authenticated using `CYBERLAB\jsmith`.
- Completed the required password change during the initial domain login.

### 5. Group Policy Configuration

- Created the GPO `CyberLab - Auto Lock 5 Minutes`.
- Configured `Interactive logon: Machine inactivity limit` to `300` seconds.
- Linked the GPO to the `Lab-Computers` OU.
- Executed `gpupdate /force` to refresh Group Policy.
- Verified policy application using `gpresult /r /scope computer` in an elevated PowerShell session.
- Confirmed that the Windows 11 client automatically locked after five minutes of inactivity.

## Verification Results

- [x] Domain controller deployed
- [x] Active Directory domain configured
- [x] Organizational Units created
- [x] User and security group configured
- [x] Windows 11 client joined to the domain
- [x] Domain user authentication verified
- [x] Group Policy created and linked
- [x] Group Policy application verified
- [x] Automatic workstation locking tested successfully

## Lessons Learned

This lab provided hands-on experience deploying and administering Active Directory Domain Services in a virtual enterprise-style environment.

Key skills developed include organizational unit management, domain user administration, security group membership, Windows domain joining, and Group Policy configuration.

Troubleshooting DNS connectivity and verifying policy application demonstrated how centralized identity management depends on reliable network configuration and communication with the domain controller.

## Screenshots

Configuration and verification screenshots may be added after review to ensure no passwords or sensitive information are exposed.

## Outcome

Successfully deployed a functional Active Directory domain with a Windows Server 2022 domain controller and a Windows 11 Pro client.

Verified domain authentication, organizational unit management, and enforcement of a five-minute workstation inactivity lock through Group Policy.
