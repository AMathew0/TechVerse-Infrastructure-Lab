# Project 1 – Hybrid Cloud Infrastructure Lab ☁️🏢

## 📅 Timeline
- Estimated Duration: 6–7 Days (Hands-On)

## 🎯 Objective
Simulate and implement a basic hybrid infrastructure using VirtualBox-hosted environments (local on-premise simulation) and GitHub for configuration management, reflecting real-world hybrid setups.

---

## 📁 Project Structure
📁 Project1-HybridInfra 

  ├── 📁 Diagrams 
  
  ├── 📁 Configs 
    
  ├── 📁 Scripts 
  
  ├── 📁 Notes 
  
  └── README.md

  
---

## 🛠️ Tools & Platforms Used

| Tool | Role |
|------|------|
| VirtualBox | VM host environment |
| Lubuntu (24.04) | Lightweight Linux VM for cloud-native simulation |
| Windows Server 2019 Eval | Simulated on-premises server |
| Windows 10 Eval | Simulated end-user workstation |
| Git & GitHub | Version control and lab management |
| PowerShell/Bash | Automation and system configuration |
| VS Code | Optional editor for scripting and documentation |

---

## 🔑 Key Skills Gained

- Understanding Hybrid Infrastructure basics
- Installing and configuring VMs
- Simulating private cloud (on-prem VM) + public cloud (GitHub & service simulation)
- Creating diagrams to represent architecture
- Writing setup/config scripts for repeatable deployment

---

## 📌 Lab Modules

### ✅ Module 1: Environment Setup
- Install and configure VirtualBox
- Create base VMs: Lubuntu, Windows Server, Windows 10
- Snapshot VMs for rollback checkpoints

### ✅ Module 2: Network Architecture & Diagram
- Design network with NAT, Host-only adapter (simulate LAN & cloud access)
- Use `draw.io` or `Excalidraw` to visualize hybrid infra topology

### ✅ Module 3: Host Configuration
- Set static IPs on Windows Server & Lubuntu
- Enable remote access (SSH/PowerShell Remoting)

### ✅ Module 4: Resource Sharing Simulation
- Create file sharing between VMs (Samba/SMB or Shared Folders)
- Simulate internal DNS or Hosts mapping
- Local Git repo sync as public cloud representation

### ✅ Module 5: Basic Monitoring & Validation
- Install lightweight tools like `htop`, `ping`, `traceroute`, or PowerShell diagnostics
- Test inter-VM connectivity and service reachability

---

## 📘 Documentation & Notes

- Store all commands/scripts in `📁 Scripts`
- Save diagrams as PNG or `.drawio` in `📁 Diagrams`
- Save notes, command history, lessons learned in `📁 Notes`

---

## ✅ Completion Criteria
- All VMs are configured and connected in a simulated hybrid network
- Basic file sharing and IP reachability working
- Diagrams and documentation completed and committed to repo

---

## 🚀 Next Project
Proceed to [Project 2 – Network Security Lab 🔒](../Project2-NetworkSecurity)
