# Sysmon Process Creation Monitoring

## Objective

Monitor process creation events using Sysmon logs.

## SPL Query

```spl
index=* EventCode=1
| table _time host User Image CommandLine ParentImage
```

## Explanation

Sysmon Event ID 1 records process creation activity.

This helps detect:

- Malware Execution
- PowerShell Abuse
- Command Prompt Activity
- Suspicious Parent-Child Processes
- Living Off The Land Attacks

## Investigation Questions

- Which process was executed?
- Who executed it?
- What was the parent process?
- Was it expected behavior?
- Is the command line suspicious?

## MITRE ATT&CK

- T1059 - Command and Scripting Interpreter
- T1204 - User Execution
```
