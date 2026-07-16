# Enterprise File Server

## Overview

The GPCTech Enterprise Lab includes a dedicated Windows Server 2022 File Server (`DLAB-SRV01-FS1`) providing centralised file storage for departmental resources.

The file server demonstrates enterprise storage management using:

- Windows File Services
- SMB Shares
- NTFS Permissions
- Active Directory Security Groups
- Access-Based Enumeration
- File Access Auditing
- Windows Storage Spaces (RAID 1)
- Integration with Splunk Enterprise and Microsoft Sentinel

---

## Objectives

- Centralised departmental storage
- Role-based access control (RBAC)
- Least privilege access
- Secure file sharing
- Auditable file activity
- Backup and recovery
- SIEM integration

---

## Storage Platform

| Component | Value |
|-----------|-------|
| Server | DLAB-SRV01-FS1 |
| Operating System | Windows Server 2022 |
| Storage | Windows Storage Spaces |
| RAID | Two-way mirror (8 TB raw / ~4 TB usable) |
| File Sharing | SMB |
| Authentication | Active Directory (`dlab.local`) |

---

## Planned Folder Structure

```text
Shares
├── Common
├── HR
├── Engineering
├── IT
├── Software
├── Projects
├── Backups
└── Personal
```

---

## Security Features

- NTFS Permissions
- Share Permissions
- Access-Based Enumeration
- File Auditing
- Security Group Access
- Centralised Authentication
- Event Logging

---

## Future Integration

Windows Security Events

↓

Splunk Enterprise

↓

Microsoft Sentinel

↓

Detection Rules

↓

n8n Automation

↓

Incident Response
