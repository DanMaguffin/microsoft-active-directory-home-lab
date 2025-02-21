# microsoft-active-directory-home-lab
A self-directed project to build and manage a virtualized Active Directory environment, simulating enterprise-level user and network management.

## Overview
This project involves setting up an Active Directory (AD) lab using VirtualBox to practice user account management, network configuration, and security policies. The lab automates routine tasks with PowerShell and integrates essential Windows services like DNS, DHCP, and file sharing.

## Features
- Automated user account provisioning, maintenance, and deprovisioning using PowerShell scripts.
- Configured Remote Access Server (RAS) with NAT/PAT support for secure network access.
- Implemented Windows DNS and DHCP services for dynamic IP management.
- Deployed a Windows File Server with NTFS permissions and storage quotas for secure file management.

## Tools Used
- VirtualBox: Virtualization platform for hosting the AD environment.
- Windows Server OS: Base operating system for AD, DNS, DHCP, and file services.
- PowerShell: Scripting for automation and management tasks.
- Windows Command Line: Configuration and troubleshooting.

## Prerequisites
- VirtualBox installed (download from [virtualbox.org](https://www.virtualbox.org/)).
- Windows Server ISO (e.g., Windows Server 2019/2022, available via evaluation from Microsoft).
- Basic familiarity with Windows networking and PowerShell.

## Setup Instructions
1. **Install VirtualBox:**
   - Download and install VirtualBox on your system.
2. **Set Up VM:**
   - Create a new VM in VirtualBox with at least 4GB RAM and 50GB storage.
   - Mount the Windows Server ISO and install the OS.
3. **Configure Active Directory:**
   - Promote the VM to a Domain Controller via Server Manager (`Add Roles and Features` > `Active Directory Domain Services`).
   - Set up a domain (e.g., `lab.local`).
4. **Add Services:**
   - Install DNS and DHCP roles via Server Manager.
   - Configure DHCP scope (e.g., 192.168.1.100-200).
   - Set up RAS with NAT (`Routing and Remote Access` tool).
5. **File Server:**
   - Create a shared folder, apply NTFS permissions (e.g., read-only for guests), and set storage quotas.
6. **Automate with PowerShell:**
   - Example script to create users:
     ```powershell
     New-ADUser -Name "TestUser" -AccountPassword (ConvertTo-SecureString "P@ssw0rd123" -AsPlainText -Force) -Enabled $true
     ```
   - Save and run scripts in PowerShell ISE.

## Outcomes
- Successfully managed a virtual AD environment with automated user provisioning.
- Demonstrated network configuration skills (DNS, DHCP, RAS) and file security best practices.
- Gained hands-on experience with PowerShell scripting for IT administration.

## Future Enhancements
- Add Group Policy Objects (GPOs) for password complexity enforcement.
- Integrate with a second VM for multi-domain testing.

## Contact
Daniel Maguffin | dmaguffin17@gmail.com 
