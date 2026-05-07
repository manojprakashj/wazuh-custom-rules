# Wazuh Custom Rules Collection

Custom detection rules for Wazuh focused on:
- Active Directory attacks
- Red team activity
- Threat hunting
- Detection engineering
- Windows attack and defense

This repository contains production ready XML rules for detecting offensive security tooling, adversary techniques, and suspicious behavior in enterprise Windows environments.

---

# Current Rule Sets

## SharpHound / BloodHound Detection Rules

Detection coverage for:
- SharpHound binary execution
- BloodHound PowerShell cmdlets
- LDAP enumeration
- CollectionMethods flags
- AD JSON artifact generation
- ZIP archive creation from collected data

### Covered Techniques
| Technique | MITRE ATT&CK |
|---|---|
| Account Discovery | T1033 |
| PowerShell Execution | T1059 |
| Archive Collected Data | T1560 |
| Masquerading / Artifact Creation | T1036 |
| Account Enumeration | T1087 |

---

## Null Session Enumeration Detection

Detects:
- Anonymous or low authentication RPC enumeration
- SAMR enumeration attempts
- LSARPC enumeration
- SRVSVC enumeration against Domain Controllers

Useful for detecting:
- Legacy enumeration techniques
- SMB reconnaissance
- Initial AD discovery activity

---

# Requirements

Recommended stack:
- Wazuh Manager 4.x+
- Sysmon installed on endpoints
- Windows event collection enabled
- Active Directory environment

Recommended Sysmon configuration:
- SwiftOnSecurity Sysmon Config
- Olaf Hartong Sysmon Modular

---

# Installation

Copy the XML rules into:

```bash
/var/ossec/etc/rules/
```

# Example : Detection telemetry for suspicious AD enumeration activity using SAMR over IPC$ shares.

<img width="1600" height="782" alt="domain-controller-1" src="https://github.com/user-attachments/assets/43c1e020-b0b4-4dd9-9860-3cce6c8872b3" />

---
