[![01 Environment](https://img.shields.io/badge/01-Environment-blue)](https://github.com/filipecastanheira-rgb/truenas-implementation-lab/tree/main/01-environment)
[![02 Storage Pools](https://img.shields.io/badge/02-Storage_Pools-green)](https://github.com/filipecastanheira-rgb/truenas-implementation-lab/tree/main/02-storage-pools)
[![03 Users & Permissions](https://img.shields.io/badge/03-Users_&_Permissions-orange)](https://github.com/filipecastanheira-rgb/truenas-implementation-lab/tree/main/03-users-permissions)
[![04 Phase 1 SMB Issues](https://img.shields.io/badge/04-Phase_1:_SMB_Issues-red)](https://github.com/filipecastanheira-rgb/truenas-implementation-lab/tree/main/04-phase1-smb-issues)
[![05 Phase 2 Shell](https://img.shields.io/badge/05-Phase_2:_Shell_Alternative-purple)](https://github.com/filipecastanheira-rgb/truenas-implementation-lab/tree/main/05-phase2-shell-alternative)
[![06 Phase 3 ACL](https://img.shields.io/badge/06-Phase_3:_ACL_Solution-brown)](https://github.com/filipecastanheira-rgb/truenas-implementation-lab/tree/main/06-phase3-acl-solution)
[![07 Phase 4 Flash](https://img.shields.io/badge/07-Phase_4:_Flash_Drive-yellow)](https://github.com/filipecastanheira-rgb/truenas-implementation-lab/tree/main/07-phase4-flash-drive)
[![08 Phase 5 SFTP](https://img.shields.io/badge/08-Phase_5:_SFTP_FileZilla-blue)](https://github.com/filipecastanheira-rgb/truenas-implementation-lab/tree/main/08-phase5-sftp-filezilla)
[![09 Security Notice](https://img.shields.io/badge/09-Security_Notice-grey)](https://github.com/filipecastanheira-rgb/truenas-implementation-lab/tree/main/09-security-notice)
[![10 Conclusion](https://img.shields.io/badge/10-Conclusion-brightgreen)](https://github.com/filipecastanheira-rgb/truenas-implementation-lab/tree/main/10-conclusion)
[![Screenshots](https://img.shields.io/badge/Screenshots-Folder-lightgrey)](https://github.com/filipecastanheira-rgb/truenas-implementation-lab/tree/main/screenshots)



# TrueNAS Implementation Lab

A hands-on laboratory documenting the installation, configuration, and troubleshooting of **TrueNAS CORE 13.0** in a virtualized environment using VMware Workstation.

Developed as part of a **Cybersecurity and Networks** technical course (CET), this project covers storage pool creation, user management, ACL permissions, SMB sharing, mapped network drives, and secure SFTP file transfer.

---

## Overview

| Item | Detail |
|------|--------|
| Platform | TrueNAS CORE 13.0-U6.7 (FreeBSD) |
| Virtualization | VMware Workstation (Windows 11 host) |
| IP Address | 192.168.139.132 (NAT) |
| Date | April 2026 |
| Author | Filipe Castanheira |

---

## Methodology

| Phase | Description |
|-------|-------------|
| **Phase 1 — Installation & Configuration** | TrueNAS installation, storage pool creation, user management, first SMB share attempt. Errors encountered and troubleshooting via PowerShell. |
| **Phase 2 — Diagnosis & Alternative Solution** | TrueNAS built-in Shell used to create and verify files directly on the server, proving the storage system was fully functional. |
| **Phase 3 — Final SMB Resolution** | Root cause identified (incorrect ACL permissions), fix applied, SMB access confirmed from Windows 11. |
| **Phase 4 — Mapped Network Drive (Flash)** | SMB share mapped as drive Z: in Windows — simulating a virtual USB pen drive. |
| **Phase 5 — SFTP via FileZilla** | Secure file transfer via SFTP using FileZilla Client connected to TrueNAS over SSH. |

---

## Lab Structure

```
truenas-implementation-lab/
├── 01-environment/
├── 02-storage-pools/
├── 03-users-permissions/
├── 04-phase1-smb-issues/
├── 05-phase2-shell-alternative/
├── 06-phase3-acl-solution/
├── 07-phase4-flash-drive/
├── 08-phase5-sftp-filezilla/
├── 09-security-notice/
├── 10-conclusion/
└── screenshots/
```

---

## Key Concepts Covered

- NAS (Network Attached Storage) fundamentals
- ZFS storage pools — Mirror (RAID-1) vs Stripe (RAID-0)
- Dataset creation and ACL permissions
- SMB (Samba) file sharing and mapped network drives
- Systematic troubleshooting methodology
- SFTP secure file transfer via SSH
- Windows 11 network drive mapping

---

## Security Notice

> All passwords used in this lab are intentionally simple for convenience in a simulation environment.
> **In production, always use strong, unique passwords for every account and service.**

---

## Final Result

> All objectives achieved:
> - TrueNAS CORE fully installed and configured
> - Mirror (RAID-1) and Stripe (RAID-0) pools operational
> - SMB access working from Windows 11
> - Network drive Z: mapped and functional (virtual USB pen drive)
> - SFTP access confirmed via FileZilla Client
