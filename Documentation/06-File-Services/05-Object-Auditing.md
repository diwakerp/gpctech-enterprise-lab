# File Access Auditing

## Purpose

Object Access Auditing records file and folder activity within the enterprise file server.

These events support security monitoring, incident investigations, and compliance reporting.

---

## Logged Events

- File Read
- File Write
- File Delete
- Permission Changes
- Folder Creation
- Folder Deletion

---

## Windows Event IDs

| Event | ID |
|--------|----|
| File Access | 4663 |
| Handle Request | 4656 |
| Permission Change | 4670 |
| Object Deleted | 4660 |

---

## SIEM Integration

Windows Security Logs

↓

Splunk Universal Forwarder

↓

Splunk Enterprise

↓

Detection Rules

↓

Microsoft Sentinel

---

## Future Detection Use Cases

- Mass file deletion
- Suspicious file access
- Privilege abuse
- Ransomware indicators
- Unauthorized permission changes
