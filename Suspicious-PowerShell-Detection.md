# Suspicious PowerShell Detection

## Objective

Detect PowerShell execution activity that may indicate malicious behavior.

## SPL Query

```spl
index=* EventCode=1 Image="*powershell.exe"
| table _time host User Image CommandLine
```

## Explanation

This query detects PowerShell process creation events from Sysmon logs.

PowerShell is frequently abused by attackers for:

- Malware Execution
- Downloading Payloads
- Credential Theft
- Privilege Escalation
- Persistence

## Investigation Questions

- Who executed PowerShell?
- What command was executed?
- Was PowerShell launched from a suspicious location?
- Was a file downloaded?
- Did the activity lead to account creation or privilege escalation?

## MITRE ATT&CK

- T1059.001 - PowerShell
- T1059 - Command and Scripting Interpreter
```
