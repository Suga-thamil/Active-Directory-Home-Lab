# Domain Controller Setup

## Objective

Install and configure Active Directory Domain Services (AD DS) on Windows Server 2022.

---

## Environment

| Component | Value |
|------------|---------|
| Server Name | DC01 |
| Operating System | Windows Server 2022 |
| Domain Name | corp.local |

---

## Steps Performed

### 1. Installed Active Directory Domain Services

- Opened Server Manager
- Added AD DS Role
- Completed installation

### 2. Promoted Server to Domain Controller

- Created a new forest
- Domain Name: corp.local

### 3. Verified Domain Controller

Verified:

```powershell
hostname
```

Output:

```text
DC01
```

---

## Result

Successfully deployed a Domain Controller for the corp.local domain.
