# Hardware Inventory

## Overview

This document provides an inventory of the physical infrastructure supporting the GPCTech Enterprise Infrastructure Lab.

The environment consists of multiple mini PC servers running enterprise workloads including Active Directory, file services, print services, security monitoring and remote management platforms.

---

# Compute Infrastructure

## DLAB-SRV01

| Attribute | Details |
|---|---|
| Manufacturer | Lenovo |
| Processor | Intel Core i5-12500 |
| RAM | 16GB |
| TPM | Enabled |
| Role | Hyper-V Virtualisation Host |

### Hosted Virtual Machines

| Hostname | Role |
|---|---|
| DLAB-SRV01-DC1 | Domain Controller / DNS |
| DLAB-SRV01-FS1 | File Server |
| DLAB-SRV01-PS1 | Print Server |

---

## DLAB-SRV02

| Attribute | Details |
|---|---|
| Manufacturer | Lenovo |
| Processor | AMD Ryzen 5 PRO 2400GE |
| RAM | 16GB |
| TPM | Enabled |
| Role | Security Monitoring Infrastructure |

### Planned Workloads

| Hostname | Role |
|---|---|
| Splunk Search / Cluster Components | SIEM Platform |
| Splunk Indexer 1 | Log Storage and Processing |

---

## DLAB-SRV03

| Attribute | Details |
|---|---|
| Manufacturer | Lenovo |
| Processor | AMD Ryzen 5 PRO 2400GE |
| RAM | 24GB |
| TPM | Enabled |
| Role | Security Monitoring Infrastructure |

### Planned Workloads

| Component | Role |
|---|---|
| Splunk Indexer 2 | Log Processing |
| Heavy Forwarder | Data Collection and Routing |

---

## DLAB-SRV04 (DL-PC-01)

| Attribute | Details |
|---|---|
| Manufacturer | Dell |
| Processor | Intel Core i5-12500T |
| RAM | 16GB |
| Operating System | Windows 11 Pro |
| Role | Management and Automation Host |

### Services

| Service | Purpose |
|---|---|
| Docker | Container Platform |
| NetLock RMM | Remote Monitoring and Management |

---

# Network Infrastructure

| Component | Technology |
|---|---|
| Internet Provider | Sky Broadband |
| Gateway | UniFi Dream Machine |
| Switching | UniFi 5-Port Switches |
| Wireless | UniFi Access Point |

---

# Storage Infrastructure

## NAS Storage

| Component | Details |
|---|---|
| Capacity | 8TB Raw Storage |
| Configuration | RAID Mirroring |
| Purpose | Centralised Storage and Backup |

Storage organisation:
Storage Pool
│
├── Common
│ └── Department Shared Data
│
└── Personal
└── Restricted User Data



---

## Access Control

Security controls implemented:

- NTFS permissions
- Folder-level access control
- User-based permissions
- Restricted personal storage

---

## Remote Access

Remote access is provided through:

- Cloudflare Tunnel
- Cloudflare Zero Trust WARP Client

This allows secure access without exposing internal services directly to the internet.
