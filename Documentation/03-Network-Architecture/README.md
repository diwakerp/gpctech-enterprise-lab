# Network Architecture

## Overview

The GPCTech Enterprise Lab uses network segmentation to separate servers, user workstations, guest devices and IoT/camera infrastructure.

The environment uses a UniFi Dream Machine as the primary gateway, firewall and routing device.

---

# Internet Connectivity
Internet
|
Sky Broadband Router
|
WAN Connection
|
UniFi Dream Machine


WAN Configuration:

| Component | Address |
|---|---|
| Sky Router | Private WAN Gateway |
| UDM WAN Interface | 192.168.0.7 |

The ISP connection uses dynamic public addressing.

---

# Internal Networks

| Network | Subnet | Purpose |
|---|---|---|
| Server Network | 192.168.1.0/24 | Infrastructure servers |
| Workstation Network | 192.168.7.0/24 | User devices |
| Guest Network | 192.168.6.0/24 | Guest internet access |
| Camera Network | TBD | IoT / Cameras |

---

# Wireless SSIDs

## APR-2 Workstations

Purpose:

- Laptop devices
- Personal workstations
- Administrative devices

Network:
192.168.7.0/24


---

## U-Wifi

Purpose:

- WiFi-enabled cameras
- IoT devices

Network:
192.168.18.0/24


---

## Sky-DD

Purpose:

- Guest wireless access
- External devices

Network:
192.168.6.0/24


---

# Network Segmentation Design
             Internet
                |
          Sky Router
                |
              UDM
                |
   -----------------------------------
   |          |            |         |
   Servers Workstations Guest       U-Wifi
192.168.1.x 192.168.7.x 192.168.6.x 192.168.18.x



---

# Security Benefits

Network separation provides:

- Reduced attack surface
- Isolation of guest devices
- Protection of server infrastructure
- Improved incident response capability
- Better visibility for security monitoring

---

# Future Improvements

Planned enhancements:

- Dedicated VLAN IDs
- Firewall rules between networks
- IDS/IPS monitoring
- Network logging to SIEM
- Automated threat detection
