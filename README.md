# DetectFailedStatusSentinelHealthTable
Failure alerts of Microsoft Sentinel Health Table

This rule detects "Failure" situtation from Microsoft Sentinel Health Table. This alerts detects issues about Data collectors, Automation rule, Playbooks, Analytics rules.
https://learn.microsoft.com/en-us/azure/sentinel/health-table-reference

# Current Scheduled KQL Query

```
SentinelHealth
| where Status == "Failure"
| project TimeGenerated, OperationName, Status, SentinelResourceId, SentinelResourceName, Description, Reason, SentinelResourceType, SentinelResourceKind
```
