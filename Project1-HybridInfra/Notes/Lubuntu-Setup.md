# 🧩 Lubuntu VM Setup – Configuration Reference

## 📅 Date:
- 2025-05-01

---

## 📌 Objective:
Set up a lightweight Lubuntu VM using VirtualBox to simulate a cloud-native environment for hybrid infrastructure lab.

---

## 💻 VM Host Environment:
- **Host OS:** Windows 11 (or your native OS)
- **Virtualization Software:** Oracle VirtualBox (v7 or later)

---

## 📥 ISO Download:
- **Lubuntu ISO**: https://cdimage.ubuntu.com/lubuntu/releases/24.04/release/

---

## ⚙️ VirtualBox VM Configuration

| Setting | Value |
|--------|--------|
| **VM Name** | `Lubuntu-HybridVM` |
| **Type** | Linux |
| **Version** | Ubuntu (64-bit) |
| **RAM** | 2048 MB (2 GB) |
| **CPU** | 2 Cores |
| **Video Memory** | 128 MB |
| **Storage** | 25–30 GB (Dynamically allocated) |
| **Network Adapter 1** | NAT (for internet) |
| **Network Adapter 2** | Host-only Adapter (for hybrid lab connectivity) |
| **Audio** | Disabled (optional) |

---

## 🧱 Installation Steps

1. Open VirtualBox → Click `New` → Name: `Lubuntu-HybridVM`
2. Assign RAM, CPU, and Storage
3. Mount downloaded Lubuntu ISO under "Optical Drive"
4. Start VM → Follow Lubuntu Installer
   - Language: English
   - Installation Type: Normal
   - Use entire disk
5. Set hostname: `lubuntu-hybrid`
6. Create user (e.g., `admin` / password: `admin123`)
7. Complete setup → Reboot → Remove ISO when prompted

---

## 🛠️ Post-Installation Config

### 🔐 1. Set Static IP (Optional)

Edit netplan config:
```bash
sudo nano /etc/netplan/01-network-manager-all.yaml

Sample static IP config (for Host-only adapter enp0s8):

network:
  version: 2
  ethernets:
    enp0s8:
      dhcp4: no
      addresses: [192.168.56.101/24]
      gateway4: 192.168.56.1
      nameservers:
        addresses: [8.8.8.8, 1.1.1.1]
Apply:

sudo netplan apply

🔄 2. Update System

sudo apt update && sudo apt upgrade -y

🧰 3. Install Essential Tools

sudo apt install openssh-server net-tools htop curl vim -y

💡 4. Enable SSH (Optional Remote Access)

sudo systemctl enable ssh
sudo systemctl start ssh

✅ 5. Validate Setup

Check IP: ip a
Ping host VM: ping 192.168.56.1
SSH test (from host):

ssh admin@192.168.56.101

📁 Optional Configs

Shared Clipboard: Enable in VirtualBox Settings → General → Advanced
Drag & Drop: Bidirectional
Shared Folders: Add host path if required (VirtualBox Devices → Shared Folders)

✅ Outcome

Lubuntu VM is now fully configured as part of the simulated hybrid infrastructure and ready for networking, scripting, and monitoring labs.

🧠 Lessons Learned

Static IP helps in consistent VM reachability.
Dual-network setup simulates LAN and internet for hybrid use cases.
Lightweight Lubuntu is efficient for nested infrastructure labs.

🔗 References
Lubuntu Official Site
Netplan Configuration Guide
VirtualBox Host-Only Networking
