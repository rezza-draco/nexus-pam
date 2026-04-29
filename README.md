# Nexus PAM – Privileged Access Management System

<p align="center">
  <img src="https://raw.githubusercontent.com/rezza-draco/nexus-pam/main/nexus2.png" width="200" alt="Nexus PAM Logo"/>
</p>

<p align="center">
  <b>One portal. All your servers. Zero compromise.</b><br/>
  Web-based PAM solution for SSH, Telnet, and RDP access — no client software needed.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-18.x-green?logo=node.js"/>
  <img src="https://img.shields.io/badge/PostgreSQL-14%2B-blue?logo=postgresql"/>
  <img src="https://img.shields.io/badge/Ubuntu-22.04%20%7C%2024.04-orange?logo=ubuntu"/>
  <img src="https://img.shields.io/badge/License-Proprietary-red"/>
  <img src="https://img.shields.io/badge/Community-Free-green"/>
  <img src="https://img.shields.io/badge/Business%2FEnterprise-Paid-blue"/>
</p>

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🖥️ SSH Terminal | Browser-based SSH terminal to Linux servers |
| 🌐 Telnet Terminal | Connect to network devices (MikroTik, Cisco, etc.) |
| 🪟 RDP Access | Remote Desktop to Windows servers via Guacamole |
| 📁 File Transfer | Upload/download files over SSH |
| 🎬 Session Recording | Record SSH sessions, export to MP4 |
| 👥 Multi-role Auth | super_admin / admin / operator / user |
| 🔐 LDAP / AD | Active Directory integration |
| 🔑 AES-256-GCM | Encrypted credential storage |
| 📊 Audit Logs | All connection activity logged |
| 🛡️ Rate Limiting | Brute-force protection on all login endpoints |

---

## 🚀 Quick Install (Ubuntu 22.04 / 24.04)

### 1. Download the installer

Go to the [**Releases**](../../releases/latest) page and download **`nexus-pam-installer.zip`**.

### 2. Upload to your server

```bash
scp nexus-pam-installer.zip user@YOUR_SERVER_IP:/home/user/
```

### 3. Extract and run

```bash
ssh user@YOUR_SERVER_IP
cd /home/user/
unzip nexus-pam-installer.zip -d nexus-pam/
cd nexus-pam/
sudo bash install.sh
```

The installer will:
- Install Node.js 18, PostgreSQL, Nginx, ffmpeg
- Create the database and generate secure random secrets
- Set up systemd service (auto-start on boot)
- Configure Nginx reverse proxy (port 80 → 3000)
- Print the super admin password at the end — **save it!**

### 4. Open in browser

```
http://YOUR_SERVER_IP/
```

---

## 🗑️ Uninstall

```bash
sudo bash uninstall.sh
```

---

## 📋 Requirements

- Ubuntu 22.04 LTS or 24.04 LTS (64-bit)
- Minimum 2 GB RAM, 20 GB storage
- Internet access during installation (for npm packages)
- Root / sudo access

**Optional (for RDP):** Docker — installer will prompt if needed.

---

## 🔒 Security

- Passwords hashed with **bcrypt (cost 12)**
- Server credentials encrypted with **AES-256-GCM**
- JWT authentication with **random 128-char secret per install**
- Rate limiting: **10 login attempts / 15 minutes per IP**
- Security headers via **Helmet.js** (CSP, HSTS, X-Frame-Options)
- All SQL queries use **parameterized statements** (no SQL injection)

---

## 📄 License & Editions

Nexus PAM uses a **Custom Proprietary License**. Read the full [LICENSE](LICENSE) file.

| Edition | Use Case | Price |
|---------|----------|-------|
| **Community** | Personal, internal IT ops, non-commercial | **Free** |
| **Business** | Commercial deployment, multi-tenant, SLA support | Contact us |
| **Enterprise** | White-label, OEM, managed service, advanced features | Contact us |

> **Community Edition is free** for internal use within a single organization.  
> Commercial use, resale, or offering PAM as a service to third parties requires a paid license.

📧 **Licensing inquiries:** rezza.zoel@gmail.com
