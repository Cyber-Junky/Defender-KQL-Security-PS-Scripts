## Controlled Folder Access Violations (Blocked Actions)

This query identifies instances where Controlled Folder Access, a feature of Microsoft Defender for Endpoint, has blocked an application from making changes to a protected folder. This is crucial for detecting potential ransomware or other malicious software attempting to tamper with sensitive files.

```kql
DeviceEvents
| where ActionType in ( "ControlledFolderAccessViolationBlocked" )
