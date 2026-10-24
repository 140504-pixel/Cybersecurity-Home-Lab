# Lab 02 — Active Directory DNS Troubleshooting & Hardening

## Objective

Troubleshoot and improve DNS configuration in a Windows Server 2022 Active Directory environment. Verify reliable domain name resolution, Domain Controller discovery, Kerberos authentication, and secure communication between the domain controller and Windows 11 client.

## Lab Environment

| Component | Configuration |
|---|---|
| Virtualization | Oracle VirtualBox |
| Domain Controller | CyberLab-DC01 — Windows Server 2022 |
| Client | CyberLab-PC01 — Windows 11 Pro |
| Domain | cyberlab.test |
| Internal Network | 192.168.100.0/24 |
| Domain Controller IP | 192.168.100.10 |
| Client IP | 192.168.100.20 |
| Network Adapters | NAT and Internal Network (intnet) |

## Problem Identified

The Active Directory DNS zone contained unwanted NAT interface addresses, including `10.0.2.15`, alongside the intended internal network addresses.

This configuration could cause domain clients to receive an address that is not reachable through the internal lab network.

## Troubleshooting and Configuration

1. Inspected the `cyberlab.test` forward lookup zone using DNS Manager.
2. Identified and removed unwanted NAT-related DNS A records.
3. Reviewed DNS client settings on both virtual machines.
4. Disabled DNS address registration on the NAT network interfaces while retaining registration on the internal interfaces.
5. Initiated DNS registration using `ipconfig /registerdns`.
6. Verified that domain and host lookups returned the intended internal IPv4 addresses.
7. Ran Active Directory DNS diagnostics using `dcdiag /test:dns`.
8. Confirmed external DNS forwarding through the configured upstream DNS server.

## Commands Used

```powershell
Get-NetAdapter
Get-DnsClient
Get-DnsClientServerAddress -AddressFamily IPv4
Get-DnsServerForwarder
ipconfig /registerdns
nslookup cyberlab.test 192.168.100.10
nslookup CyberLab-DC01.cyberlab.test 192.168.100.10
nslookup CyberLab-PC01.cyberlab.test 192.168.100.10
dcdiag /test:dns
nltest /dsgetdc:cyberlab.test
whoami
klist
nltest /sc_verify:cyberlab.test
```

## Verification Results

| Test | Result |
|---|---|
| Domain Controller hostname resolution | Passed |
| Windows 11 client hostname resolution | Passed |
| Domain Controller discovery | Passed |
| Domain user identity | Verified |
| Kerberos Ticket Granting Ticket | Present |
| LDAP service tickets | Present |
| Kerberos encryption | AES-256 |
| Computer secure channel | Passed |
| External DNS forwarding | Passed |

The Windows 11 client successfully discovered `CyberLab-DC01` at `192.168.100.10`.

Kerberos tickets were issued to the `jsmith` domain account by the Domain Controller.

The secure channel verification returned `NERR_Success` for both the trusted DC connection and trust verification.

## Known Diagnostic Warnings

`dcdiag /test:dns` reported warnings related to the NAT adapter's dynamic IP address and DNS record registration.

These warnings remained after intentionally disabling DNS registration on the NAT interface. Core DNS resolution and Active Directory authentication tests succeeded.

The warnings are documented for future review rather than considered fully resolved.

## Skills Developed

- Active Directory DNS troubleshooting
- DNS A records and dynamic registration
- Multihomed Domain Controller configuration
- PowerShell network diagnostics
- Domain Controller discovery
- Kerberos authentication verification
- Secure channel troubleshooting

## Outcome

Successfully verified DNS resolution, Active Directory Domain Controller discovery, Kerberos authentication, and the Windows client secure channel in a virtual domain environment.

The lab improved understanding of how DNS configuration affects domain authentication and communication.
