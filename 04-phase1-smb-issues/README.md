# 04 — Phase 1: SMB Configuration and Issues

## Initial SMB Share Configuration

An SMB share was created via the TrueNAS Web UI pointing to `/mnt/Mirror/dados`, with the SMB service enabled and Samba authentication active for `utilizador1`.

| Parameter | Value |
|-----------|-------|
| Share Name | partilha |
| Path | /mnt/Mirror/dados |
| SMB Service | Active |
| Samba Auth | Enabled for utilizador1 |

---

## Errors Encountered

All access attempts from Windows 11 failed with the following errors:

| Error Code | Description |
|------------|-------------|
| Error 67 | The network name cannot be found — Windows refused the SMB connection |
| Error 86 | The specified network password is not correct |
| Error 0x80004005 | Unspecified error — generic SMB client block |

---

## Troubleshooting Attempts via PowerShell

The following approaches were attempted to resolve the issue:

- Enable SMB1 on Windows (`Enable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol`)
- Disable SMB signing (`Set-SmbClientConfiguration -RequireSecuritySignature $false`)
- Disable Windows Firewall (`netsh advfirewall set allprofiles state off`)
- Add credentials manually via Windows Credential Manager
- Use `net use` and `New-PSDrive` in PowerShell and CMD as Administrator
- Enable NTLMv1 Auth and SMB1 on the TrueNAS server
- Reconfigure Samba passwords with `smbpasswd`

**None of the above resolved the issue.** SMB access remained blocked.

---

## Diagnostic Commands Used

```bash
# Check if SMB daemon is running (TrueNAS Shell)
ps aux | grep smbd

# Check if port 445 is listening
netstat -an | grep 445

# List Samba users
pdbedit -L

# Test SMB connection from TrueNAS Shell
smbclient -L localhost -U utilizador1
```

```powershell
# Test connectivity from Windows PowerShell
ping 192.168.139.132

# Test SMB port
Test-NetConnection -ComputerName 192.168.139.132 -Port 445

# Attempt to map network drive
net use Z: \\192.168.139.132\partilha /user:utilizador1 1234
```

---

## Conclusion of Phase 1

SMB access could not be established at this stage. The root cause was not yet identified. The decision was made to find an alternative approach to prove the storage system was functional while continuing to investigate the SMB issue.
