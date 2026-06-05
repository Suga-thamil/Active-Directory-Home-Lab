# Active Directory Home Lab

## Project Overview

This project documents the creation of a Windows Active Directory home lab using Oracle VirtualBox, Windows Server 2022, and Windows 11.

The purpose of this lab is to gain hands-on experience with:

- Active Directory Domain Services (AD DS)
- DNS Configuration
- Domain User Management
- Organizational Units (OUs)
- Group Policy Objects (GPOs)
- Kerberos Authentication
- Windows Event Logging
- Security Auditing

---

## Lab Environment

### Virtual Machines

| Machine | Operating System | Role |
|----------|-----------------|------|
| DC01 | Windows Server 2022 | Domain Controller |
| CLIENT01 | Windows 11 | Domain-Joined Workstation |

### Domain Information

| Setting | Value |
|----------|---------|
| Domain Name | corp.local |
| Domain Controller | DC01 |
| Client Workstation | CLIENT01 |

---

## Technologies Used

- Oracle VirtualBox
- Windows Server 2022
- Windows 11
- Active Directory Domain Services
- DNS
- Group Policy Management
- Event Viewer
- PowerShell

---

## Project Objectives

- Deploy Active Directory Domain Services
- Create and manage domain users
- Join a workstation to the domain
- Organize resources using Organizational Units
- Configure Group Policy Objects
- Enable logon auditing
- Monitor security events
- Investigate authentication activity

---

## Active Directory Structure

```text
corp.local
│
├── Employees
│   ├── Alice Johnson
│   ├── Bob Smith
│   └── Charlie Brown
│
├── Workstations
│   └── CLIENT01
│
├── Servers
│
└── Managed Service Accounts
```

---

## Security Auditing

Configured Group Policy to audit:

- Successful Logons
- Failed Logons

Relevant Event IDs:

| Event ID | Description |
|-----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |

---

## Lessons Learned

During this project I learned:

- DNS is critical for Active Directory functionality.
- Kerberos authentication depends heavily on proper DNS configuration.
- Domain users and computers can be organized using OUs.
- Group Policy can be used to centrally manage security settings.
- Windows Event Viewer provides valuable security auditing information.
- Security events can be used to investigate authentication activity.

---

## Future Improvements

- Password Policy GPO
- Account Lockout Policy
- File Server Configuration
- Shared Folder Permissions
- Additional Workstations
- Security Information and Event Management (SIEM)
- Windows Event
- Security Monitoring Enhancements
- SIEM Integration
