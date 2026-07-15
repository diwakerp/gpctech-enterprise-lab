# Server Inventory

## Overview

This document contains details of the servers deployed within the DLAB enterprise infrastructure environment.

The environment uses Hyper-V virtualisation where multiple Windows Server workloads are hosted on physical mini PC infrastructure.

---

# Server Naming Convention

Example:

DLAB-SRV01-DC1

Breakdown:

| Segment | Meaning |
|---|---|
| DLAB | Development Lab Environment |
| SRV01 | Physical Server Host |
| DC1 | Domain Controller Instance |

---

# Physical Hosts

| Hostname | Type | Purpose |
|---|---|---|
| DLAB-SRV01 | Bare Metal Mini PC | Hyper-V Virtualisation Host |

---

# Virtual Servers

| Hostname | Operating System | Role | Status |
|---|---|---|---|
| DLAB-SRV01-DC1 | Windows Server | Domain Controller / DNS | Active |
| DLAB-SRV01-FS1 | Windows Server | File Server | Active |
| DLAB-SRV01-PS1 | Windows Server | Print Server | Active |

---

# Virtualisation Platform

Platform:

- Microsoft Hyper-V

Purpose:

- Host multiple enterprise workloads
- Simulate production infrastructure
- Enable isolated server deployments

---

# Future Servers

Planned:

- Security Monitoring Platform
- Microsoft Sentinel Integration
- Wazuh Server
- Automation Platform
