# GPCTech Enterprise Lab
# Network Architecture v1.0

## Overview

The GPCTech Enterprise Lab implements a segmented network architecture designed to simulate an enterprise environment.

Network segmentation is implemented to separate:

- Server infrastructure
- User workstations
- Guest devices
- IoT / camera devices

The environment uses a UniFi Dream Machine (UDM) as the core gateway, firewall and routing device.

---

# High-Level Network Architecture

```mermaid
flowchart TB

Internet((Internet))

Sky[Sky Broadband Router<br/>WAN Gateway]

UDM[UniFi Dream Machine<br/>Gateway / Firewall / Router<br/>WAN: 192.168.0.7]

Switch[UniFi Switch Infrastructure]

Internet --> Sky
Sky --> UDM
UDM --> Switch


Switch --> Servers[SERVER NETWORK<br/>192.168.1.0/24]

Switch --> Workstations[WORKSTATION NETWORK<br/>192.168.7.0/24]

Switch --> Guest[GUEST NETWORK<br/>192.168.6.0/24]

Switch --> Cameras[CAMERA / IoT NETWORK<br/>192.168.18.0/24]


Servers --> DC[DLAB-SRV01-DC1<br/>Domain Controller]
Servers --> FS[DLAB-SRV01-FS1<br/>File Server]
Servers --> PS[DLAB-SRV01-PS1<br/>Print Server]

Workstations --> Clients[Laptops<br/>Desktop Devices]

Guest --> GuestDevices[Guest Devices]

Cameras --> CCTV[WiFi Cameras]


UDM --> Cloudflare[Cloudflare Zero Trust]

Cloudflare --> Tunnel[Cloudflare Tunnel<br/>Docker Connector]

Tunnel --> Internal[Private Lab Resources]


| Network             | Subnet          | Purpose              | Security Level |
| ------------------- | --------------- | -------------------- | -------------- |
| Server Network      | 192.168.1.0/24  | Enterprise servers   | High           |
| Workstation Network | 192.168.7.0/24  | User devices         | Medium         |
| Guest Network       | 192.168.6.0/24  | Internet-only access | Low            |
| Camera Network      | 192.168.18.0/24 | IoT/CCTV devices     | Restricted     |


| Network             | Subnet          | Purpose              | Security Level |
| ------------------- | --------------- | -------------------- | -------------- |
| Server Network      | 192.168.1.0/24  | Enterprise servers   | High           |
| Workstation Network | 192.168.7.0/24  | User devices         | Medium         |
| Guest Network       | 192.168.6.0/24  | Internet-only access | Low            |
| Camera Network      | 192.168.18.0/24 | IoT/CCTV devices     | Restricted     |

-----
IP Address Management
Address Allocation Method

The environment uses:

UniFi Dream Machine DHCP service
DHCP reservations for infrastructure devices
Dedicated network ranges for each device category

-----
Server Network Example
192.168.1.0/24

DLAB-SRV01-DC1
Domain Controller
DNS

DLAB-SRV01-FS1
File Services

DLAB-SRV01-PS1
Print Services

DLAB-SRV02
Splunk Infrastructure

DLAB-SRV03
Splunk Infrastructure

DLAB-SRV04
NetLock RMM

-------
Remote Access Architecture

The environment does not rely on static public IP addressing.

Remote connectivity is provided through Cloudflare Zero Trust.

Architecture:
Remote Device
      |
Cloudflare WARP Client
      |
Cloudflare Edge
      |
Cloudflare Tunnel
      |
Docker Host
      |
Internal Resources

Benefits:
No inbound port exposure
No dependency on static IP
Secure remote access
Identity-based authentication
Automatic recovery after ISP IP changes

Security Considerations

Implemented:

✅ Network segmentation
✅ Firewall-controlled routing
✅ Separate guest network
✅ IoT isolation
✅ Zero Trust remote access
✅ DHCP reservations for infrastructure

Future improvements:

VLAN documentation
Firewall rule documentation
IDS/IPS monitoring
SIEM network visibility


---

