# Shared Folder Design

## Overview

The GPCTech Enterprise Lab file server uses SMB shares to provide centralised storage.

The design separates shared resources, user data, departmental data and personal storage.

---

# Share Layout

| Share | Location | Purpose |
|---|---|---|
| Common | E:\Shares\Common | Shared documents |
| Personal | F:\Shares\Personal | User private folders |
| Departments | F:\Shares\Departments | Department resources |
| Family and Friends | F:\Shares\Family and Friends | Personal storage |

---
---
# Department Structure
Departments

├── HR
├── Engineering
└── IT

---
Description
| Share       | Purpose                                   |
| ----------- | ----------------------------------------- |
| Common      | Shared company resources                  |
| HR          | Human Resources documentation             |
| Engineering | Engineering documentation                 |
| IT          | Administrative scripts and infrastructure |
| Software    | Software repository                       |
| Family and Friends    | File share access to some family and friends for data backup                     |
| Personal    | User personal storage                     |

---

# Storage Design

Storage is provided using Windows Storage Spaces with mirrored storage for resilience.

---

# Security Model

Each share will use:

Share Permissions
NTFS Permissions
Active Directory Groups
Auditing
Access-Based Enumeration

No permissions are assigned directly to users.

**#Evidence**

---

# 03-NTFS-Permissions.md

```markdown
# NTFS Permissions

## Purpose

NTFS permissions provide granular access control to files and folders within the enterprise file server.

The environment follows Microsoft's recommended Role-Based Access Control (RBAC) model by assigning permissions through Active Directory security groups rather than individual user accounts.

---

## Permission Strategy

Users

↓

Global Groups

↓

Domain Local Groups

↓

NTFS Permissions

↓

Shared Folder

---

## Security Principles

- Least Privilege
- Role-Based Access Control
- Centralized Permission Management
- Simplified Administration
- Auditable Access

---

## Planned Security Groups

| Group | Department |
|--------|------------|
| GG-HR | Human Resources |
| GG-ENGINEERING | Engineering |
| GG-IT | IT |
| GG-PROJECTS | Projects |
| GG-SOFTWARE | Software |
| GG-BACKUP | Backup Operators |
| GG-PERSONAL | Personal Storage |

---

## Benefits

- Easier administration
- Reduced permission complexity
- Better auditing
- Enterprise scalability

---

## Evidence

![Permissions](../../Screenshots/File-Server/05-share-permissions.png)

![NTFS](../../Screenshots/File-Server/06-ntfs-permissions.png)
