# Group Policy and Auditing

## Objective

Configure Group Policy to audit successful and failed logon events within the Active Directory environment.

---

## Organizational Unit

The policy was linked to the Workstations Organizational Unit.

```text
Workstations
└── CLIENT01
```

---

## Group Policy Object

Created GPO:

```text
Audit Policy
```

---

## Configuration

Navigation:

```text
Computer Configuration
 └─ Policies
     └─ Windows Settings
         └─ Security Settings
             └─ Advanced Audit Policy Configuration
                 └─ Audit Policies
                     └─ Logon/Logoff
```

Configured:

### Audit Logon

| Setting | Status |
|----------|---------|
| Success | Enabled |
| Failure | Enabled |

---

## Policy Deployment

Applied Group Policy using:

```powershell
gpupdate /force
```

Result:

```text
Computer Policy update has completed successfully.
User Policy update has completed successfully.
```

---

## Verification

Verified that security logon events were generated in Event Viewer after policy deployment.

Location:

```text
Event Viewer
 └─ Windows Logs
     └─ Security
```

---

## Lessons Learned

- Group Policy provides centralized security management.
- Audit policies can be used to monitor authentication activity.
- Policies can be targeted to specific Organizational Units.
- gpupdate /force applies policy changes immediately.

---

## Result

Successfully configured and deployed logon auditing using Group Policy.
