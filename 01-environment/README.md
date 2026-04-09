# 01 — Environment and Infrastructure

## Virtualization Platform

The lab was implemented in a virtualized environment using VMware Workstation as the hypervisor, running on a Windows 11 host machine.

---

## Virtual Machine Specifications

| Component | Detail |
|-----------|--------|
| Guest OS | TrueNAS CORE 13.0-U6.7 (FreeBSD) |
| Hypervisor | VMware Workstation |
| Host OS | Windows 11 25H2 |
| Boot Disk | 1 × 15 GB (SCSI virtual) |
| Mirror Pool Disks | 2 × 10 GB (SCSI virtual) |
| Stripe Pool Disks | 2 × 10 GB (SCSI virtual) |
| Total Virtual Disks | 5 |
| RAM | 4 GB |
| CPU | 2 vCPUs |
| Network | NAT |
| IP Address | 192.168.139.132 |
| Web UI | http://192.168.139.132 |

---

## Disk Layout

```
┌─────────────────────────────────────┐
│  Disk 1 (15 GB)  →  TrueNAS OS Boot │
│  Disk 2 (10 GB)  ┐                  │
│  Disk 3 (10 GB)  ┘→  Mirror Pool    │
│  Disk 4 (10 GB)  ┐                  │
│  Disk 5 (10 GB)  ┘→  Stripe Pool    │
└─────────────────────────────────────┘
```

---

## Notes

- All disks were created as SCSI virtual disks in VMware
- Network adapter set to NAT to allow communication with the Windows 11 host
- TrueNAS Web UI accessible via browser on the host machine
