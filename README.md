# 🛡️ System Hardening Lab (Manual Method – Windows 11 + Ubuntu 24.04)

This lab simulates a junior analyst securing systems in a realistic IT environment by manually configuring users, applying system policies, disabling unnecessary services, and enforcing security controls — all without automation.

💡 Unlike my **IAM_Lab**, which uses PowerShell scripts to automate user/group creation, this lab focuses entirely on **manual configuration** using GUI tools (like `lusrmgr.msc`, `secpol.msc`) and Linux terminal commands.

---

## 🎯 Lab Objectives
- Apply password and lockout policies (Windows + Ubuntu)
- Create and assign users and groups manually
- Disable insecure or unnecessary services
- Configure host-based firewalls (Windows Defender, UFW)
- Document changes with screenshots and test results

---

## 💻 Lab Environment

| Component | Description |
|-----------|-------------|
| OS 1      | Windows 11 Pro (Manual Setup) |
| OS 2      | Ubuntu 24.04 LTS (Terminal Only) |
| Tools     | VMware Workstation or VirtualBox |

---

## 🔐 Manual IAM Setup (Windows + Ubuntu)

### 🪟 Windows 11
- Tool used: `lusrmgr.msc` (Local Users and Groups)
- Users: `AdminZakiya`, `AnalystUser`, `GuestUser`, `SVC_Audit`
- Groups: `Administrators`, `SecTeam`, `Audit`
- Group Assignments:
  - `AdminZakiya` → Administrators
  - `AnalystUser` → SecTeam
  - `SVC_Audit` → Audit

### 🐧 Ubuntu 24.04
- Tool used: Terminal commands (`adduser`, `addgroup`, `usermod`)
- Users: `adminzakiya`, `analystuser`, `guestuser`, `svc_audit`
- Groups: `admin`, `secops`, `audit`
- Group Assignments:
  - `adminzakiya` → `sudo`, `admin`
  - `analystuser` → `secops`
  - `svc_audit` → `audit`

---

## 🔒 System Hardening Techniques

### Windows 11
- Disabled: Remote Registry, Telnet, SSDP, Print Spooler (optional)
- Set password/lockout policies via `secpol.msc`
- Enabled Windows Defender + Firewall
- Configured firewall rules (blocked PowerShell + RDP, enabled logging)

### Ubuntu 24.04
- Updated packages: `sudo apt update && sudo apt upgrade -y`
- Disabled SSH root login
- Enforced password complexity via PAM
- Enabled UFW firewall, default deny all, allow SSH

---

## 📷 Documentation

This lab includes:
- Full report (PDF)
- Step-by-step screenshots
- Folder structure separating Windows and Ubuntu configs
- Lessons learned + final reflection

---

## 🚀 Related Lab

📁 Also check out my [IAM_Lab (PowerShell Automation)](https://github.com/zakiya/IAM_Lab)  
Automated approach to user/group creation, NTFS folder permissions, and access validation on Windows 11.

---

## 🧠 Skills Practiced
- System administration (Windows + Linux)
- IAM setup (manual method)
- Host-based firewall configuration
- Report writing + documentation
- OS hardening techniques for entry-level security analysts

---

> \"Manually configured. Professionally documented.\"
