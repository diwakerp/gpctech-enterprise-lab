## Advanced Audit Policy

The workstation security baseline enables Advanced Audit Policies to improve security visibility and support SIEM integration.

### Configured Audit Categories

| Category | Configuration |
|----------|---------------|
| Account Logon | Success, Failure |
| Logon/Logoff | Success, Failure |
| Account Management | Success, Failure |
| Policy Change | Success |
| Privilege Use | Success, Failure |
| System | Success, Failure |

### Evidence

![Advanced Audit Policy](../../Screenshots/Group-Policy/05-advanced-audit-policy.png)

### Security Benefit

These audit settings generate Windows Security Events that are collected by Splunk Universal Forwarder and will later be ingested into Microsoft Sentinel. They provide visibility into authentication activity, account management, privilege escalation attempts and system integrity changes.
