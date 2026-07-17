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

# Department Structure
Departments

├── HR
├── Engineering
└── IT


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
