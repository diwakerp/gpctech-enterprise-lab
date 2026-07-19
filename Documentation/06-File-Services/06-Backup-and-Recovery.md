# Backup and Disaster Recovery

## Overview

The GPCTech Enterprise Lab includes a dedicated backup infrastructure designed to protect critical services and support disaster recovery scenarios.

Backups are managed using **Veeam Backup & Replication**, providing image-level backups of the virtual infrastructure and server workloads.

---

## Backup Infrastructure

| Component | Value |
|----------|-------|
| Backup Server | DLAB-SRV03 |
| Backup Software | Veeam Backup & Replication |
| Storage | 10 TB External Storage |
| Backup Type | Image-Level Backup |
| Virtualization Platform | Microsoft Hyper-V |

---

## Protected Systems

Current protected workloads include:

- Domain Controller
- File Server
- Print Server
- Splunk Infrastructure
- Hyper-V Host Configuration
- Active Directory
- DNS
- Group Policy Objects (GPOs)

Future protected workloads will include:

- Docker Containers
- Container Volumes
- Self-hosted Applications
- SIEM Components
- n8n Automation Platform

---

## Backup Strategy

The environment follows the **Grandfather-Father-Son (GFS)** backup rotation model.

| Backup Type | Schedule |
|------------|----------|
| Daily Incremental | Every Day |
| Weekly Full | Every Week |
| Monthly Full Archive | Every Month |

Retention Period:

- 3 Months

---

## Backup Objectives

The strategy is designed to provide:

- Rapid system recovery
- Protection against accidental deletion
- Recovery from ransomware events
- Hardware failure resilience
- Configuration rollback capability

---

## Disaster Recovery Process

In the event of server failure:

1. Restore the virtual machine using Veeam Backup & Replication.
2. Verify Hyper-V configuration.
3. Validate Active Directory replication and core services.
4. Confirm application availability.
5. Resume normal business operations.

---

## Enterprise Security Features

- Centralized backup management
- Scheduled backup verification
- Image-based recovery
- Hyper-V workload protection
- Long-term retention (3 months)
- External backup repository

---

## Future Enhancements

Planned improvements include:

- Immutable backup storage
- Off-site backup replication
- Azure Backup integration
- Backup encryption at rest
- Automated backup health reporting

---

## Backup Architecture

```text
Hyper-V Hosts
        │
        ▼
Veeam Backup & Replication
        │
        ▼
DLAB-SRV03
        │
        ▼
10 TB External Backup Repository
        │
        ▼
Daily • Weekly • Monthly (GFS)
```

---

## Evidence

![Veeam Backup Console](../../Screenshots/File-Server/09-veeam-console.png)

![Backup Jobs](../../Screenshots/File-Server/10-veeam-backup-jobs.png)

![Backup Repository](../../Screenshots/File-Server/11-backup-repository.png)

![Successful Backup History](../../Screenshots/File-Server/12-backup-history.png)
