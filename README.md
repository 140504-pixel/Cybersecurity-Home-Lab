# Cybersecurity Home Lab

## Project Overview

This project documents my hands-on experience building and managing a virtual IT infrastructure environment using Oracle VirtualBox, Windows Server 2022, and Windows 11 Pro.

The goal is to develop practical skills in Windows Server administration, Active Directory, identity and access management, Group Policy, networking, and cybersecurity fundamentals.

## Lab Environment

| Component | Configuration |
|---|---|
| Virtualization | Oracle VirtualBox |
| Domain Controller | Windows Server 2022 |
| Client Operating System | Windows 11 Pro |
| Active Directory Domain | `cyberlab.test` |
| Domain Controller VM | `CyberLab-DC01` |
| Client VM | `CyberLab-PC01` |
| Virtual Networking | NAT and Internal Network (`intnet`) |

## Completed Activities

- Installed and configured Windows Server 2022.
- Deployed Active Directory Domain Services (AD DS).
- Created the `cyberlab.test` domain.
- Created organizational units for IT users and lab computers.
- Created and managed Active Directory user accounts.
- Created an IT security group and assigned membership.
- Practiced user account administration and password resets.
- Created a Group Policy Object to enforce a 5-minute inactivity lock.
- Installed Windows 11 Pro as a virtual client.

## Verified Lab Results — 23 October 2026

- Successfully joined `CyberLab-PC01` to the `cyberlab.test` domain.
- Configured client networking and resolved DNS connectivity issues.
- Confirmed domain authentication using `CYBERLAB\jsmith`.
- Successfully tested the required domain-user password change.
- Verified the computer object in the `Lab-Computers` OU.
- Confirmed `CyberLab - Auto Lock 5 Minutes` using `gpresult /r /scope computer`.
- Verified automatic Windows screen locking after five minutes of inactivity.

**Milestone: Active Directory domain join and Group Policy testing completed successfully.**

## Completed Labs

- [Lab 01 — Active Directory Setup](docs/01-active-directory-setup.md)
- [Lab 02 — DNS Troubleshooting & Hardening](02-dns-troubleshooting.md)


## Next Lab Activities

- Configure and test Active Directory account lockout policies.
- Enable and investigate Windows security auditing.
- Analyze successful and failed authentication events using Event Viewer.
- Practice Active Directory security hardening and least-privilege administration.

## Skills Developed

- Windows Server Administration
- Active Directory Domain Services
- Identity and Access Management
- Group Policy Management
- Virtualization
- Windows Networking
- IT Troubleshooting
- DNS Configuration and Troubleshooting
- Kerberos Authentication
- Active Directory Security Diagnostics
- PowerShell Administration

## Project Status

**In Progress** — This repository will be updated as additional lab exercises are completed.
