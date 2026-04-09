# 07 — Conclusion

## Objectives Achieved

- TrueNAS CORE 13.0 installed on a 15 GB virtual boot disk
- Mirror pool (RAID-1) created with 2 × 10 GB disks — with redundancy
- Stripe pool (RAID-0) created with 2 × 10 GB disks — without redundancy
- Datasets, user with permissions and SMB share configured
- SMB access problem diagnosed and resolved (incorrect ACL permissions)
- Storage functionality proven via TrueNAS Shell (Phase 2)
- SMB access from Windows 11 proven via File Explorer (Phase 3)

---

## Lessons Learned

### Technical

- ACL permissions in TrueNAS must be explicitly configured — a dataset created without a valid ACL preset will block all external access
- The OPEN preset is suitable for lab environments; in production, more restrictive ACLs should be applied
- SMB Error 67 does not necessarily indicate a protocol or network issue — it can be caused by permission blocks at the filesystem level
- The TrueNAS built-in Shell is a powerful diagnostic and management tool

### Methodological

- When facing a blocked path, find an alternative route to prove progress and isolate the problem
- Document every error and every attempt — this creates a troubleshooting trail that helps identify the root cause
- Always distinguish between symptoms and root causes — the errors pointed to a network/protocol issue, but the actual cause was ACL permissions
- Validate the solution with concrete, reproducible tests

---

## Environment Summary

| Component | Detail |
|-----------|--------|
| TrueNAS Version | CORE 13.0-U6.7 |
| Pools | Mirror (RAID-1) + Stripe (RAID-0) |
| Total Storage | 40 GB (virtual) |
| Users | utilizador1 |
| SMB Share | dados (/mnt/stripe/dados) |
| Final Status | Fully operational |

---

## Possible Next Steps

- Configure snapshots for automated backup
- Set up replication between pools
- Enable SSH access for remote administration
- Migrate to TrueNAS SCALE for improved compatibility with modern clients
- Configure Active Directory integration for enterprise authentication

---

*Laboratory developed by Filipe Castanheira — CET Cybersecurity and Networks, April 2026*
