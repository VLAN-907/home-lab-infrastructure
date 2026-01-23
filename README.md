# Home Network Lab Documentation

Welcome to my personal network lab project! This repository documents the design, configuration, and ongoing development of my home network and lab environment. The goal is to improve my skills in network engineering, firewall management, VLAN segmentation, VPN configuration, and infrastructure documentation — while building a secure, segmented, and scalable network at home.

---

## Table of Contents  

- [Overview](#overview)  
- [Lab Hardware](#lab-hardware)  
- [Network Topology](#network-topology)  
- [Services & Tools](#services--tools)  
- [VLAN Design](#vlan-design)  
- [VPN Configuration](#vpn-configuration)  
- [DNS & Security](#dns--security)  
- [Backup & Monitoring](#backup--monitoring)
- [Future Plans](#future-plans)

---

## Overview  

This lab uses **OPNsense** as the core firewall/router with VLAN segmentation, **Pi-hole** for ad-blocking and DNS filtering, **OpenDNS** for DNS security, and various hardware components like managed switches and wireless access points.  

The lab is designed to simulate small-to-mid-sized network environments while providing a secure and scalable infrastructure for real-world use and future experimentation.

---

## Lab Hardware  

| Device                  | Purpose                       |
|:------------------------|:------------------------------|
| Custom OPNsense Firewall | Router/Firewall/VLAN Manager   |
| TP-Link Smart Switch     | VLAN segmentation, Trunk ports |
| Synology RT6600ax        | Wireless Access Point          |
| Ubuntu Server VM         | Jellyfin, Pi-hole, WireGuard    |
| Various Client Devices   | Test devices (phones, laptops) |

---

## Network Topology  

[Network Diagram](./diagrams/LabSetupDiagram.png)


---

## Services & Tools  

- **OPNsense** — Firewall, Routing, VLAN Management  
- **WireGuard VPN** — Remote secure access  
- **Pi-hole** — DNS Filtering and Ad Blocking [Link to more info](./docs/pihole.md) 
- **OpenDNS** — Cloud-based DNS Security  
- **Unbound (DNS Resolver)** — Internal DNS resolution  
- **Ubuntu Server** — Media services and Pi-hole
- **Security Onion** - IDS (Intrusion Detction), NSM (Network Security Monitoring), Log Management and Threat Hunting [Link to more info](./docs/SecurityOnion.md) 

---

## VLAN Design  

| VLAN ID | Name        | Subnet         | Purpose                |
|:--------|:------------|:----------------|:------------------------|
| 10      | LAN          | 192.168.10.0/24 | Default Untagged         |
| 20      | Trusted      | 192.168.20.0/24 | Trusted Devices          |
| 30      | IoT          | 192.168.30.0/24 | IoT/Smart Devices        |
| 40      | Guest        | 192.168.40.0/27 | Guest WiFi               |
| 50      | Cameras      | 192.168.50.0/24 | IP Cameras               |
| 70      | Media        | 192.168.70.0/24 | Streaming devices/Jellyfin|
| 99      | Management   | 192.168.99.0/24 | Network device management|

---

## VPN Configuration  

- **WireGuard** VPN set up on OPNsense for secure remote access  


---

## DNS & Security  

- **Pi-hole** for DNS ad-blocking  
- **OpenDNS** for cloud-based DNS filtering  
- **Unbound DNS Resolver** configured for internal resolution with forwarding enabled

---

## Backup & Monitoring  

- Future integration: Reg Config Backups via OPNsense, Firmware update plan and scnapshot schedule, syslog, NTP monitoring, and SNMP stats collection

---

## Future Plans
- Evaluate **Docker-based deployment** for easier portability
- Integrate with existing **home network services** (DNS, backup systems)
- Potential public-facing deployment with a domain and secure remote access

---

## Related Technologies
- Ubuntu Server 22.04 LTS
- Apache2
- MySQL or MariaDB
- PHP 8.x
- Let's Encrypt (Certbot)
- Webtrees 2.x

---

*This project reflects my ongoing efforts to build a secure, private, and reliable platform for family tree management while developing practical system administration skills in my home lab.*

---

## Future Plans  


[Future Projects](./docs/Future-Projects.md)



---

## Contact  

If you're interested in this project or have suggestions, feel free to connect with me on LinkedIn or reach out via GitHub Issues.

