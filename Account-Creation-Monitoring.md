# Account Creation Monitoring

## Objective

Detect newly created user accounts within Windows Security Logs.

## SPL Query

```spl
index=* EventCode=4720
| table _time host Subject_Account_Name Target_Account_Name
```

## Explanation

Event ID 4720 indicates a new user account was created.

This query helps identify:

- Unauthorized Account Creation
- Persistence Mechanisms
- Insider Threat Activity
- Privilege Escalation Attempts

## Investigation Questions

- Who created the account?
- When was the account created?
- Was the account added to any privileged groups?
- Was the account used for login activity?
```
