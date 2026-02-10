# Home Network Lab Infrastructure

This repository documents my home network and lab environment, built to develop practical skills in network engineering, firewall policy management, VLAN segmentation, and infrastructure documentation — while maintaining a secure and usable home network.

---

## Table of Contents
- [Overview](#overview)
- [Current Architecture](#current-architecture)
- [Lab Hardware](#lab-hardware)
- [Network Topology](#network-topology)
- [VLAN Design](#vlan-design)
- [DNS & Security](#dns--security)
- [Monitoring & Backups](#monitoring--backups)


---

## Overview

The lab is centered around a Cisco router acting as the core Layer 3 gateway for routing, segmentation, and policy enforcement. Wireless access is provided by a Ubiquiti UniFi U7 Pro access point, with the UniFi Network Application hosted on-premises for centralized device management and visibility. DNS filtering is handled by Pi-hole, with the environment documented through diagrams and configuration notes to reflect real operational practices.

Previously, this lab ran on OPNsense; it has since been migrated to a Cisco router as part of building deeper hands-on experience with Cisco-based routing and segmentation.

---

## Current Architecture

**Primary goals:**
- Secure separation of untrusted/IoT devices from trusted devices
- Simple, reliable home network operation
- Room to expand into additional segmentation, monitoring, and remote access over time

**Core components:**
- Managed switching with VLAN tagging/trunking
- Pi-hole DNS filtering
- OpenDNS upstream filtering

---

## Lab Hardware

| Device                    | Purpose                                |
|:--------------------------|:----------------------------------------|
| TP-Link Managed Switch    | VLAN tagging, trunk/access ports        |
| Ubuntu Server VM          | Pi-hole and supporting services         |
| Client Devices            | Phones, laptops, IoT devices            |
|Ubiquiti UniFi U7 Pro | Wireless Access Point (Wi-Fi 7)              |
|Ubuntu Server VM | UniFi Network Application, Pi-hole                |

---

## Network Topology

[Network Diagram](./diagrams/LabSetupDiagram.png)

---

## VLAN Design

Current segmentation is intentionally simple and reflects the current production setup:

| VLAN / Network | Subnet          | Purpose                     |
|:--------------|:-----------------|:----------------------------|
| LAN           | 192.168.1.0/24    | Trusted user devices        |
| IoT           | 192.168.2.0/24    | Smart home / IoT devices    |

**Policy approach:**
- Inter-VLAN access is restricted by firewall rules (default-deny posture where applicable)
- IoT devices are limited to required outbound access and specific allowed destinations/services

---

## DNS & Security

- **Pi-hole** provides DNS-level filtering (ads/malware domains)
- **OpenDNS** provides upstream DNS security filtering

Documentation and notes:
- Pi-hole: [docs/pihole.md](./docs/pihole.md)

---

## Monitoring & Backups

Planned / in-progress operational controls include:
- Firmware update / maintenance plan
- Syslog collection
- NTP validation/monitoring
- SNMP metrics collection (where supported)

---

## Retired / Previously Tested

These were deployed or evaluated at one time but are not currently in use:

- **Unbound DNS resolver** (replaced/removed to simplify DNS path)
- **WireGuard VPN** (evaluated; may be reintroduced as part of a future remote-access design)

---

## Future Plans

- Expand segmentation beyond two VLANs as requirements grow (e.g., Guest, Management)
- Add centralized logging and better monitoring/alerting
- Revisit secure remote access (VPN) with documentation and threat-model-driven rules
- Evaluate containerization where it improves portability and maintainability

---

## Contact

If you're interested in this project or have suggestions, feel free to connect with me on LinkedIn or reach out via GitHub Issues.
