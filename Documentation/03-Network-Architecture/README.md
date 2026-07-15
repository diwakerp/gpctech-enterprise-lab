# Network Architecture

## Overview

This document describes the network architecture of the GPCTech Enterprise Infrastructure Lab.

The design represents a small enterprise environment containing internal servers, user endpoints, networking equipment and secure remote access capabilities.

---

# Current Architecture
Internet
|
ISP Router
|
UniFi Gateway
|
Network Switch
|
Servers / Clients



---

# Network Components

| Component | Technology | Purpose |
|---|---|---|
| Gateway | UniFi | Routing and firewall |
| Switch | UniFi | Internal connectivity |
| Servers | Windows Server | Infrastructure services |
| Clients | Windows | User endpoints |

---

# Future Security Enhancements

- VLAN segmentation
- Network monitoring
- Firewall logging
- SIEM integration
- Zero Trust access
