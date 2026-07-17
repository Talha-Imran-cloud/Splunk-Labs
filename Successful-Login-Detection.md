# Successful Login Detection

## Objective

Detect successful login events within Windows Security Logs.

## SPL Query

```spl
index=* EventCode=4624
| table _time host Account_Name Source_Network_Address Logon_Type
```

## Explanation

Event ID 4624 indicates a successful login.

This query helps identify:

- User Login Activity
- Unusual Login Times
- Suspicious Login Locations
- Account Usage Monitoring
```
