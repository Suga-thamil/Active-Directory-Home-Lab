# Domain Join and DNS Troubleshooting

## Objective

Join a Windows 11 workstation (CLIENT01) to the Active Directory domain and troubleshoot domain connectivity issues.

---

## Environment

| Component | Value |
|------------|---------|
| Domain Controller | DC01 |
| Domain | corp.local |
| Client Workstation | CLIENT01 |
| DNS Server | 192.168.56.10 |

---

## Problem Encountered

The client workstation was unable to properly communicate with the Active Directory domain.

Symptoms included:

- Domain login issues
- Authentication failures
- Domain resources not being discovered correctly

---

## Investigation

### DNS Verification

Checked domain name resolution:

```cmd
nslookup corp.local
```

Result:

```text
Name:    corp.local
Address: 192.168.56.10
```

---

### Active Directory Service Records

Verified LDAP SRV records:

```cmd
nslookup -type=SRV _ldap._tcp.dc._msdcs.corp.local
```

Result:

```text
_ldap._tcp.dc._msdcs.corp.local SRV service location:
          port = 389
          svr hostname = dc01.corp.local
```

This confirmed that Active Directory DNS records were correctly registered.

---

## Domain Join

The workstation was successfully joined to:

```text
corp.local
```

Verification:

```powershell
(Get-WmiObject Win32_ComputerSystem).Domain
```

Output:

```text
corp.local
```

---

## Authentication Testing

Successfully authenticated using a domain account:

```cmd
whoami
```

Output:

```text
corp\alice
```

This confirmed successful domain authentication.

---

## Computer Account Management

The workstation account was moved into the dedicated Workstations Organizational Unit.

```text
Workstations
└── CLIENT01
```

This allows future Group Policies to be applied specifically to workstation systems.

---

## Lessons Learned

- Active Directory relies heavily on DNS.
- Domain controllers must be discoverable through DNS service records.
- Successful domain authentication depends on proper DNS configuration.
- Organizational Units help organize and manage domain resources.
- Troubleshooting DNS should be one of the first steps when investigating domain connectivity issues.

---

## Result

Successfully joined CLIENT01 to the corp.local domain and verified domain authentication through Active Directory.
