## Finds all PowerShell execution events wherein the PowerShell window has been explicitly hidden.

```kql
DeviceProcessEvents
| where Timestamp > ago(7d)
| where InitiatingProcessFileName =~ "powershell.exe"
| where InitiatingProcessCommandLine has "-Command"
| where InitiatingProcessCommandLine has "-w hidden" or InitiatingProcessCommandLine has "-windowstyle hidden"
| project Timestamp, DeviceName, InitiatingProcessCommandLine
| top 100 by Timestamp
