# 09 — Security Notice

## Lab Environment Disclaimer

> All passwords used throughout this lab were set to a simple value for convenience and to avoid mistakes during testing.
>
> **This practice is strictly for lab and simulation environments only.**

---

## Password Best Practices for Production

In a real-world or production environment, always follow these guidelines:

| Practice | Description |
|----------|-------------|
| Strong passwords | Minimum 12 characters combining uppercase, lowercase, numbers and symbols |
| Unique passwords | Different password for each account and service — never reuse |
| Password manager | Use a password manager to store credentials securely |
| Regular rotation | Change passwords periodically, especially after staff changes |
| No shared accounts | Each user must have their own individual account |
| MFA | Enable Multi-Factor Authentication wherever possible |

---

## TrueNAS Specific Recommendations

- Never use `root` for day-to-day operations — create dedicated admin accounts
- Disable unused services (FTP, Telnet) — only enable what is needed
- Restrict SSH access to specific IP addresses where possible
- Apply the principle of least privilege — users should only have access to what they need
- Use restrictive ACL presets in production (not OPEN) — configure per-user permissions
- Enable audit logging to track access and changes

---

*Security is not a feature — it is a practice.*
