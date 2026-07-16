# Active Directory Architecture

## Overview

The GPCTech Enterprise Lab uses Microsoft Active Directory Domain Services (AD DS) to provide centralised identity management, authentication and policy management.

The Active Directory environment simulates an enterprise domain where users, computers and servers are centrally managed.

---

# Domain Information

| Component | Details |
|---|---|
| Domain Name | TBD |
| Forest Name | TBD |
| Domain Controller | DLAB-SRV01-DC1 |
| Operating System | Windows Server |
| Services | AD DS, DNS |

---

# Domain Controller

## DLAB-SRV01-DC1

Role:

- Active Directory Domain Controller
- DNS Server
- Authentication Provider
- Group Policy Management

---

# Logical Architecture

```mermaid
flowchart TB

Users["Users"]

Devices["Workstations"]

DC["DLAB-SRV01-DC1<br>Active Directory Domain Controller"]

DNS["DNS Service"]

GPO["Group Policy"]

Users --> DC

Devices --> DC

DC --> DNS

DC --> GPO

#Authentication Flow
User Device

     |
     |
Domain Authentication

     |
     |
Active Directory

     |
     |
Access Granted

Core Services
| Service                          | Purpose                  |
| -------------------------------- | ------------------------ |
| Active Directory Domain Services | Identity management      |
| DNS                              | Name resolution          |
| Group Policy                     | Configuration management |
| Kerberos                         | Authentication           |
| LDAP                             | Directory queries        |


Future Security Enhancements

Planned:

LAPS implementation
Privileged access management
Account auditing
Authentication monitoring
SIEM integration


---

# Step 3 — I need your actual AD details

Do not guess. Tell me your current setup.

Reply with:

## 1. Domain name

Example:
Dlab.local

---

## 2. Windows Server version

Example:
Windows Server 2022 Standard

---

## 3. Domain Controller IP

Example:
192.168.1.11

---
