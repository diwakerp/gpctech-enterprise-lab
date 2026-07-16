# Active Directory Documentation

## Overview

This section documents the Active Directory Domain Services implementation within the GPCTech Enterprise Lab.

Active Directory provides centralised identity management, authentication, DNS integration and policy management for the Windows infrastructure.

---

# Environment Details

| Component | Details |
|---|---|
| Domain | dlab.local |
| Domain Controller | DLAB-SRV01-DC1 |
| IP Address | 192.168.1.11 |
| DHCP Provider | UniFi Dream Machine |
| DNS Provider | Active Directory Integrated DNS |
| Hypervisor | Microsoft Hyper-V |

---

# Active Directory Components

The environment contains:

- Active Directory Domain Services
- DNS Server
- Users and Groups
- Organizational Units
- Group Policy Management

---

# Documentation Index

| Document | Description |
|---|---|
| Active Directory Overview | Domain architecture |
| Domain Configuration | Domain settings |
| OU Structure | Organizational design |
| Users and Groups | Identity management |
| DNS | Name resolution |
| Security | Hardening and monitoring |

---

# Architecture

```mermaid
flowchart TB

User["Users"]

PC["Workstations"]

DC["DLAB-SRV01-DC1<br>Domain Controller"]

DNS["DNS"]

GPO["Group Policy"]

User --> PC
PC --> DC
DC --> DNS
DC --> GPO
