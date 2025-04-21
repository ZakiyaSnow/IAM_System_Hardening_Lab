# 🛡️ IAM & System Hardening Lab (Manual Method – Windows 11 + Ubuntu 24.04)

This project demonstrates a manual approach to configuring **Identity and Access Management (IAM)** and **System Hardening** using the built-in tools in **Windows 11** and **Ubuntu 24.04 LTS**.

The goal is to simulate a realistic IT environment where users, groups, and security policies are managed using GUI and terminal interfaces instead of automation scripts — great for junior analysts and sysadmins in training.

---

## 🎯 Lab Objectives

- Configure IAM using built-in tools (Computer Management, terminal)
- Apply password, lockout, and access restrictions
- Harden systems by reducing attack surface and enabling firewalls
- Learn how to manually configure users and monitor system activity
- Document each change with screenshots and test results

---

## 💻 Lab Environment

| Component | Description |
|----------|-------------|
| OS 1     | Windows 11 Pro |
| OS 2     | Ubuntu 24.04 LTS |
| Tool     | VMware Workstation or Player |

---

## 🧑‍💻 IAM Setup (Manual Method)

### 🪟 Windows 11

**Tool used:** `lusrmgr.msc` (Computer Management)

#### 🔹 Users Created:
- `AdminZakiya` – Local Administrator
- `AnalystUser` – Standard User
- `GuestUser` – Guest Access
- `SVC_Audit` – Service Account

#### 🔹 Groups Created:
- `SecTeam` – Added `AnalystUser`
- `Audit` – Added `SVC_Audit`

#### 🔹 Group Assignments:
- `AdminZakiya` → added to `Administrators`
- `AnalystUser` → added to `SecTeam`
- `SVC_Audit` → added to `Audit`

---

### 🐧 Ubuntu 24.04

**Tool used:** Terminal (`adduser`, `usermod`, `addgroup`)

#### 🔹 Users Created:
- `adminzakiya`
- `analystuser`
- `guestuser`
- `svc_audit`

#### 🔹 Groups Created:
- `admin`
- `secops`
- `audit`

#### 🔹 Group Assignments:
- `adminzakiya` → `sudo`, `admin`
- `analystuser` → `secops`
- `svc_audit` → `audit`

---

## 🔒 System Hardening

### 🪟 Windows 11

- Disabled **Remote Registry**, **Telnet**, and unused services via `services.msc`
- Set **account lockout** and **password policies** via `secpol.msc`
- Enabled **Windows Defender** and **Firewall**
- Configured **Windows Firewall with Advanced Security**:
  - Blocked inbound PowerShell and RDP
  - Enabled firewall logging for all profiles

### 🐧 Ubuntu 24.04

- Updated system packages:
  ```bash
  sudo apt update && sudo apt upgrade -y
