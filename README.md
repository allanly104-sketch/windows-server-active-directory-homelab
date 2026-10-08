# windows-server-active-directory-homelab
Windows Server 2022 Active Directory homelab with Windows 11, DNS, domain joining, and help desk troubleshooting.
# Windows Server 2022 Active Directory Homelab

## Project Overview

This project documents my hands-on experience building a small Windows Active Directory environment using Oracle VirtualBox.

The goal was to develop practical IT support skills, including network configuration, DNS troubleshooting, domain joining, user account management, and password resets.

## Lab Environment

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Domain Controller | Windows Server 2022 |
| Client Computer | Windows 11 Pro |
| Domain | homelab.test |
| Domain Controller IP | 192.168.10.1 |
| Client IP | 192.168.10.10 |
| Internal Network | LabNet |

## Network Configuration

Configured an internal VirtualBox network to allow the Windows 11 client to communicate with the Domain Controller.

Verified network connectivity using `ping` and confirmed DNS resolution using `nslookup`.

<img width="1522" height="812" alt="network-DNS-verification" src="https://github.com/user-attachments/assets/e379f778-6e45-43a7-8ccf-4444172d87a5" />


## Active Directory Domain Join

Installed and configured Active Directory Domain Services on Windows Server 2022.

Created the `homelab.test` domain and successfully joined the Windows 11 client to the domain.

<img width="839" height="652" alt="domain-join-success" src="https://github.com/user-attachments/assets/bc7c92fe-8251-44be-be54-ab9a67208c7d" />


## Help Desk Scenario: Password Reset

Created a test user account in Active Directory and practiced resetting the user's password using Active Directory Users and Computers.

This simulated a common Tier 1 IT Help Desk support task.

<img width="814" height="576" alt="Ative-Directory-password-reset" src="https://github.com/user-attachments/assets/82e3cb35-e78a-4f25-b1b2-4f111130d15d" />


## Domain User Authentication

Successfully signed into Windows 11 using the domain test account.

Verified the authenticated user through Command Prompt using:

`whoami`

Result: `homelab\testuser`

<img width="919" height="513" alt="domain-user-authentication" src="https://github.com/user-attachments/assets/e0863118-4f9f-4d60-b373-5e611fa1eea1" />


## DNS Troubleshooting

During testing, I discovered that the domain's DNS records included the VirtualBox NAT IP address (`10.0.2.15`) in addition to the internal Domain Controller address (`192.168.10.1`).

To correct this:

1. Disabled DNS address registration on the Domain Controller's NAT adapter.
2. Removed the unwanted NAT Host (A) record.
3. Verified that the domain resolved to the correct internal IPv4 address using `nslookup`.

## Skills Practiced

- Windows Server 2022 administration
- Active Directory Domain Services
- Windows 11 domain joining
- IPv4 addressing and DNS configuration
- User account administration and password resets
- Command-line troubleshooting
- VirtualBox virtual networking

## Future Improvements

- Configure Group Policy Objects (GPOs)
- Practice shared-folder and NTFS permissions
- Configure DHCP
- Simulate additional IT Help Desk troubleshooting scenarios

---

*This project was completed in a virtual lab environment for IT learning and portfolio development.*
