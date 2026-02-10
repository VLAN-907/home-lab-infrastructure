# Resilient Core Services Lab (DHCP/DNS + Backups)

## Overview
This lab demonstrates the design and implementation of resilient core infrastructure services using Windows Server, spanning multiple hypervisors and backed up to TrueNAS. The goal is to achieve **service-level high availability** for DHCP and DNS, independent of hypervisor HA, while maintaining safe and restorable backups.

This project intentionally focuses on **identity and network services**, not application workloads.

## Goals
- Redundant Active Directory–integrated DNS
- DHCP failover between two Windows Servers
- Service resiliency across separate hypervisors (VMware + Proxmox)
- Backups to TrueNAS with documented restore procedures
- Clear validation tests and lessons learned

## Non-Goals
- Hypervisor-level HA as a dependency
- Load balancers or advanced network appliances
- Production-scale AD complexity

## Architecture Summary
- DC1: Windows Server on VMware
- DC2: Windows Server on Proxmox
- Shared LAN/VLAN
- TrueNAS as centralized backup target

## Documentation
- [Network Design](docs/01-network-design.md)
- [Build Notes](docs/02-build-notes.md)
- [DHCP Failover](docs/03-dhcp-failover.md)
- [DNS Design](docs/04-dns-design.md)
- [Backups & Restore](docs/05-backups-and-restore.md)
- [Testing & Validation](docs/06-testing-and-validation.md)
- [Lessons Learned](docs/07-lessons-learned.md)

## Status
✔ Completed core services  
✔ Backups verified  
⬜ Optional VMware HA sprint (future)

## Next Steps
- DFS Namespace + Replication
- AD CS (Certificate Services)
- WSUS or patch management
- Proxmox Backup Server integration
