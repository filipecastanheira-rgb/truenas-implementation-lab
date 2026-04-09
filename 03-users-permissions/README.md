# 03 — Users and Permissions

## User Created

| Parameter | Value |
|-----------|-------|
| Username | utilizador1 |
| Full Name | Utilizador Teste |
| Samba Authentication | Enabled |
| Dataset Permissions | Read + Write + Execute |
| Path | /mnt/Mirror/dados |

---

## How to Create a User in TrueNAS

1. Go to **Accounts → Users → Add**
2. Fill in **Full Name** and **Username**
3. Set a password
4. Ensure **Samba Authentication** is checked
5. Click **Save**

---

## How to Set Dataset Permissions

1. Go to **Storage → Pools**
2. Click the **three dots (⋯)** next to the dataset
3. Select **Edit Permissions**
4. Set the **User** to your created user
5. Check **Read**, **Write**, and **Execute**
6. Click **Save**

---

## Security Note

> In this lab environment, a simple password was used for convenience.  
> In a production environment, always use strong passwords (minimum 12 characters, mixing uppercase, lowercase, numbers and symbols) following security best practices.
