## Finds the first appearance of files sent by a malicious sender in your organization

```kql
#replace the malicious sender with the actual malicious sender information
let MaliciousSender = "malicious.sender@domain.com";
EmailAttachmentInfo
| where Timestamp > ago(30d)
| where SenderFromAddress =~ MaliciousSender
| join (
DeviceFileEvents
| where Timestamp > ago(30d)
) on SHA256
| summarize FirstAppearance = min(Timestamp) by DeviceName, SHA256, FileName
