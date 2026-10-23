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

## Work in Progress

- Configure communication between the Windows Server and Windows 11 virtual machines.
- Join Windows 11 Pro to the Active Directory domain.
- Test domain authentication and Group Policy application.
- Document configuration steps and verification results.

## Skills Developed

- Windows Server Administration
- Active Directory Domain Services
- Identity and Access Management
- Group Policy Management
- Virtualization
- Windows Networking
- IT Troubleshooting

## Project Status

**In Progress** — This repository will be updated as additional lab exercises are completed.
