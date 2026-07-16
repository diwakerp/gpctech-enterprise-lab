# Windows Security Logging

## Overview

The GPCTech Enterprise Lab is configured to generate Windows security telemetry for centralised monitoring.

Primary log sources include:

- Security Event Log
- System Event Log
- Application Event Log
- PowerShell Operational Log
- Microsoft Defender Operational Log

These logs are collected by the Splunk Universal Forwarder and will later be ingested into Microsoft Sentinel.

---

## Planned Event Sources

| Source | Purpose |
|----------|---------|
| Security | Authentication and account events |
| System | Operating system events |
| Application | Application errors and warnings |
| PowerShell | Script execution monitoring |
| Defender | Malware and endpoint protection |

---

## SIEM Integration

Windows Event Logs

↓

Splunk Universal Forwarder

↓

Splunk Enterprise

↓

Microsoft Sentinel

↓

Detection Rules

↓

Incident Response
