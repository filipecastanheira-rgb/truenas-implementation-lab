# 02 — Storage Pools

Two storage pools were created to demonstrate different RAID configurations and their trade-offs.

---

## Pool 1 — Mirror (RAID-1)

Data written to one disk is automatically replicated to the second disk. If one disk fails, data remains intact on the surviving disk.

| Parameter | Value |
|-----------|-------|
| Pool Name | Mirror |
| Type | Mirror (RAID-1) |
| Disks | da1 + da2 (10 GB each) |
| Usable Capacity | 10 GB |
| Redundancy | Yes — tolerates 1 disk failure |
| Dataset | /mnt/Mirror/dados |
| Status | ONLINE |

---

## Pool 2 — Stripe (RAID-0)

Data is distributed across both disks, doubling available capacity. No redundancy — if one disk fails, all data is lost.

| Parameter | Value |
|-----------|-------|
| Pool Name | stripe |
| Type | Stripe (RAID-0) |
| Disks | da3 + da4 (10 GB each) |
| Usable Capacity | 20 GB |
| Redundancy | None — total data loss if 1 disk fails |
| Dataset | /mnt/stripe/dados |
| Status | ONLINE |

---

## Mirror vs Stripe — Comparison

| | Mirror (RAID-1) | Stripe (RAID-0) |
|-|-----------------|-----------------|
| Redundancy | Yes | No |
| Usable capacity | 50% of total | 100% of total |
| Read performance | Higher | Higher |
| Write performance | Same | Higher |
| Fault tolerance | 1 disk failure | None |
| Use case | Critical data | Performance / temp data |

---

## How to Create a Pool in TrueNAS

1. Go to **Storage → Pools → Add**
2. Select **Create a new pool**
3. Enter a pool name
4. Select the disks and move them to **Data VDevs**
5. Choose the layout: **Mirror** or **Stripe**
6. Click **Create**
