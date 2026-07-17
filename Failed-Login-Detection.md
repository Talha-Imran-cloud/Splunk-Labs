# Failed Login Detection

## Objective

Detect failed login attempts within Windows Security Logs.

## SPL Query

```spl
index=* EventCode=4625
| table _time host Account_Name Source_Network_Address Logon_Type
```

## Explanation

Event ID 4625 indicates a failed login attempt.

This query helps identify:

- Brute Force Attempts
- Invalid Login Activity
- Unauthorized Access Attempts
```
