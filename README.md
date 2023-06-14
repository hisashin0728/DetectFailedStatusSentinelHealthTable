# DetectFailedStatusSentinelHealthTable
Failure alerts of Microsoft Sentinel Health Table

This rule detects "Failure" situtation from Microsoft Sentinel Health Table. This alerts detects issues about Data collectors, Automation rule, Playbooks, Analytics rules.
https://learn.microsoft.com/en-us/azure/sentinel/health-table-reference

# Install
Import json file from Microsoft Sentinel
<img width="940" alt="image" src="https://github.com/hisashin0728/DetectFailedStatusSentinelHealthTable/assets/55295601/b1e3e004-7c3c-47c8-9645-e3e2e53efcec">

# Alerts
Current Settings is follow:<p>
<img width="271" alt="image" src="https://github.com/hisashin0728/DetectFailedStatusSentinelHealthTable/assets/55295601/998226a9-3a14-4fae-b363-4d4ddd030454">

Alert Name:
``{{SentinelResourceType}} failed about {{SentinelResourceName}}``
Alert Desription:
``{{Description}}, Reason code is {{Reason}}.``


# Current Scheduled KQL Query

```
SentinelHealth
| where Status == "Failure"
| project TimeGenerated, OperationName, Status, SentinelResourceId, SentinelResourceName, Description, Reason, SentinelResourceType, SentinelResourceKind
```

<img width="686" alt="image" src="https://github.com/hisashin0728/DetectFailedStatusSentinelHealthTable/assets/55295601/5ae7dcd0-27c1-4d86-9176-9bb1a657d4ec">


