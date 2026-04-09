# 10 — Conclusion

## Objectives Achieved

| # | Objective | Status |
|---|-----------|--------|
| 1 | TrueNAS CORE 13.0 installed on 15 GB virtual boot disk | Done |
| 2 | Mirror pool (RAID-1) — 2 × 10 GB with redundancy | Done |
| 3 | Stripe pool (RAID-0) — 2 × 10 GB without redundancy | Done |
| 4 | Datasets, user with permissions and SMB shares configured | Done |
| 5 | SMB access problem diagnosed and resolved (incorrect ACL) | Done |
| 6 | Storage functionality proven via TrueNAS Shell (Phase 2) | Done |
| 7 | SMB access from Windows 11 confirmed (Phase 3) | Done |
| 8 | Network drive Z: mapped in Windows — virtual USB pen drive (Phase 4) | Done |
| 9 | Secure SFTP access via FileZilla Client (Phase 5) | Done |

---

## Access Methods Demonstrated

| Method | Protocol | Tool | Result |
|--------|----------|------|--------|
| Shell access | Local | TrueNAS Web UI Shell | File created and verified |
| Network share | SMB | Windows File Explorer | Full read/write access |
| Mapped drive | SMB | Windows File Explorer | Drive Z: mounted as flash |
| Secure transfer | SFTP/SSH | FileZilla Client | Connection established, files verified |

---

## Lessons Learned

### Technical
- ACL permissions in TrueNAS must be explicitly configured — a dataset without a valid ACL preset blocks all external access
- SMB Error 67 does not always indicate a network or protocol issue — it can be caused by ACL blocks at the filesystem level
- SFTP (port 22) is always preferable to FTP (port 21) in any environment — it provides encrypted, secure file transfer
- TrueNAS supports multiple simultaneous access protocols — SMB for Windows users, SFTP for administrators

### Methodological
- When facing a blocked path, find an alternative route to prove progress and isolate the problem
- Document every error and every attempt — this creates a troubleshooting trail that helps identify the root cause
- Always distinguish between symptoms and root causes
- Validate every solution with concrete, reproducible tests

---

## Environment Summary

| Component | Detail |
|-----------|--------|
| TrueNAS Version | CORE 13.0-U6.7 |
| Pools | Mirror (RAID-1) + Stripe (RAID-0) |
| Total Virtual Storage | 40 GB |
| Users | utilizador1 |
| SMB Shares | dados + flash |
| SFTP | Enabled (SSH port 22) |
| Final Status | Fully operational |

---

## Possible Next Steps

- Configure automated snapshots for backup
- Set up pool replication between Mirror and Stripe
- Enable SSH key-based authentication (disable password auth)
- Migrate to TrueNAS SCALE for improved compatibility with modern clients
- Configure Active Directory integration for enterprise authentication
- Set up email alerts for pool health monitoring

---

*Laboratory developed by Filipe Castanheira — CET Cybersecurity and Networks, April 2026*
