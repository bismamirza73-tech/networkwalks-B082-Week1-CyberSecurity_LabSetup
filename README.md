# 🔐 VirtualBox + Kali Linux Sandbox Lab Setup

### 🛡️ Complete Cybersecurity Lab Environment Configuration

A safe and isolated cybersecurity laboratory environment built using **Oracle VirtualBox** and **Kali Linux** for practicing penetration testing, security tools, network security, and ethical hacking techniques.

---

# 📋 Repository Overview

This repository contains the complete documentation and configuration process for creating an **isolated cybersecurity lab environment** using Oracle VirtualBox and Kali Linux.

The purpose of this lab is to provide a safe and controlled environment where cybersecurity concepts and security tools can be practiced without affecting the host system or production network.

---

# 📦 Repository Contents

| 📁 Component             | 📝 Description                                  |
| ------------------------ | ----------------------------------------------- |
| 📚 Documentation         | Complete step-by-step lab setup documentation   |
| 🖼️ Screenshots          | Screenshots of configuration and testing stages |
| 🛠️ Troubleshooting      | Common issues encountered and their solutions   |
| 🌐 Network Configuration | IP, DNS, gateway, and NAT network configuration |
| 💾 Backup Strategy       | VM snapshots and backup procedures              |
| 🎓 Learning Outcomes     | Skills and cybersecurity concepts developed     |
| 🎥 Video Demonstration   | Short walkthrough of the completed lab          |

---

# 🎯 Lab Purpose & Objectives

## 🔬 Why a Sandbox Environment?

The sandbox environment provides a controlled space for cybersecurity learning and experimentation.

* 🔐 Provides an isolated testing environment
* 🛡️ Prevents accidental damage to the host system
* 🧪 Allows safe experimentation with security tools
* 🔄 Creates reproducible testing scenarios
* 📊 Allows controlled network monitoring
* 🎓 Supports practical cybersecurity learning

## 🌐 Why an Isolated Network?

The lab uses an isolated NAT Network to separate the virtual environment from other devices and networks.

* Complete network segmentation
* Controlled IP addressing
* Safe vulnerability scanning
* Reduced risk to other devices
* Controlled network-based security testing

---

# 🖥️ Lab Environment Specifications

| ⚙️ Component                | 💻 Configuration               |
| --------------------------- | ------------------------------ |
| **Host Operating System**   | Windows 11 Pro (22H2)          |
| **Host RAM**                | 16 GB DDR4                     |
| **Host CPU**                | Intel Core i7-10750H @ 2.60GHz |
| **Host Storage**            | 512 GB NVMe SSD                |
| **Virtualization Platform** | Oracle VirtualBox 7.0.12       |
| **Guest Operating System**  | Kali Linux 2024.1              |
| **VM RAM Allocation**       | 8 GB                           |
| **VM CPU Cores**            | 4 Cores                        |
| **VM Storage**              | 50 GB Dynamically Allocated    |
| **Network Type**            | NAT Network                    |
| **Network Subnet**          | `10.0.0.0/24`                  |
| **Gateway IP**              | `10.0.0.1`                     |
| **Kali VM IP**              | `10.0.0.2`                   |
| **DNS Servers**             | `8.8.8.8`, `8.8.4.4`           |

---

# 🛠️ Tasks Completed

## 1️⃣ 7-Zip Installation

* Installed 7-Zip archiver
* Verified `.ova` file extraction
* Prepared the Kali Linux VirtualBox image for deployment

## 2️⃣ VirtualBox Installation

* Installed Oracle VirtualBox
* Verified successful installation
* Prepared the virtualization environment

## 3️⃣ NAT Network Configuration

* Created an isolated NAT Network
* Configured subnet `10.0.0.0/24`
* Configured IP addressing
* Ensured network isolation

## 4️⃣ Kali Linux VM Deployment

The Kali Linux VirtualBox image was imported with the following configuration:

| ⚙️ Setting        | 🔧 Configuration |
| ----------------- | ---------------- |
| **RAM**           | 8 GB             |
| **CPU**           | 4 Cores          |
| **Video Memory**  | 128 MB           |
| **Storage**       | 50 GB            |
| **PAE/NX**        | Enabled          |
| **VT-x/AMD-V**    | Enabled          |
| **Nested Paging** | Enabled          |

## 5️⃣ Kali Linux IP Configuration

* Static IP: `10.0.0.2/24`
* Gateway: `10.0.0.1`
* DNS: `8.8.8.8`
* Verified network connectivity
* Updated system packages

## 6️⃣ VM Snapshot Creation

# ✅ Verification & Testing

## 🌐 Network Configuration Validation

```bash
# IP Configuration Check
ip a

# Gateway Connectivity
ping -c 4 10.0.0.1

# Internet Connectivity
ping -c 4 google.com

# DNS Resolution
nslookup kali.org

# Routing Table
route -n
```

### ✔️ Expected Results

* Kali IP: `10.0.0.2/24`
* Gateway: `10.0.0.1`
* Network connectivity verified
* DNS resolution working
* Default route available

---

# 🖥️ System Verification

```bash
# Kali Linux Version
lsb_release -a

# Kernel Version
uname -r

# Available Disk Space
df -h

# Memory Usage
free -h
```

### ✔️ Verification Results

* **Kali Linux:** 2024.1
* **Kernel:** 6.6.0-kali1-amd64
* **RAM:** 8 GB recognized
* **Storage:** Sufficient for cybersecurity tools

---

# 🐛 Challenges Encountered & Resolutions

## ❌ Issue 1 — Network Interface Not Detected

**Problem:**
The Kali VM had no active network interface after import.

**Solution:**
Modified the network configuration and restarted the networking service.

```bash
sudo systemctl restart networking
```

> ✅ **Status: Resolved**

---

## ❌ Issue 2 — NAT Network Not Available

**Problem:**
The NAT Network option was not available in the VM settings.

**Solution:**
Created the NAT Network through VirtualBox Network Manager before configuring the VM.

> ✅ **Status: Resolved**

---

# 📸 Screenshots Documentation

The lab documentation includes screenshots covering:

1. 🧰 7-Zip Installation
   ```markdown

---
3. 🖥️ VirtualBox Installation
4. 🌐 NAT Network Creation
5. 💻 Kali VM Import
6. 🌐 IP Configuration
7. 📡 Network Verification
8. 🔄 System Update
9. 💾 Snapshot Creation
10. 🖥️ Running Kali VM
11. ⚙️ Network Manager Configuration

> 📌 **Screenshots can be stored inside a `screenshots/` directory in this repository.**

Example:

```markdown
![Kali IP Configuration](screenshots/ip-configuration.png)


---

# 💾 Snapshot & Backup Strategy

## 📌 Snapshot Points

| 📸 Snapshot            | 📝 Description                               | 🎯 Purpose               |
| ---------------------- | -------------------------------------------- | ------------------------ |
| **Base Clean Install** | Fresh Kali installation with working network | Starting point           |
| **Tools Installed**    | Essential security tools installed           | Save reinstallation time |
| **Pre-Experiment**     | Created before risky operations              | Quick rollback           |

## 🗓️ Backup Schedule

| ⏱️ Frequency             | 💾 Backup Action                          |
| ------------------------ | ----------------------------------------- |
| **Daily**                | Export VM to external SSD                 |
| **Weekly**               | Upload compressed backup to cloud storage |
| **Monthly**              | Archive all snapshots                     |
| **Before Major Changes** | Create a new backup                       |

## 📁 Backup Locations

```text
Local:    D:\VirtualBox VMs\Kali_Lab_Backups\
External: E:\Kali_Lab_Backups\
Cloud:    Google Drive / OneDrive
```

---

# 📚 Learning Outcomes

## 🖥️ Virtualization Skills

* Understanding Type-2 hypervisor architecture
* VM resource allocation
* Snapshot management
* Virtual networking
* NAT, Bridged, and Host-Only networking

## 🌐 Networking Knowledge

* IP addressing
* Subnetting
* Static and DHCP configuration
* DNS resolution
* Routing
* Network troubleshooting

## 🐧 Linux Administration

* Debian-based Linux administration
* CLI network configuration
* APT package management
* System service management
* Linux troubleshooting

## 🔐 Cybersecurity Concepts

* Network isolation
* Sandbox environments
* Controlled security testing
* Risk mitigation
* Safe experimentation

---

# 🔧 Tools & Technologies

| 🧰 Tool / Technology  | 🎯 Purpose                        |
| --------------------- | --------------------------------- |
| **Oracle VirtualBox** | Virtual machine management        |
| **Kali Linux**        | Cybersecurity testing environment |
| **Linux CLI**         | System administration             |
| **7-Zip**             | `.ova` file extraction            |
| **ping**              | Network connectivity testing      |
| **nslookup**          | DNS testing                       |
| **ip**                | Network configuration             |
| **route**             | Routing table inspection          |
| **Git**               | Version control                   |
| **Obsidian**          | Documentation                     |

---

# 📖 Resources & References

* [7-Zip](https://7-zip.org/)
* [Oracle VirtualBox](https://virtualbox.org/)
* [Kali Linux](https://kali.org/)
* [Git](https://git-scm.com/)
* [Obsidian](https://obsidian.md/)
* [PuTTY](https://putty.org/)
* [WinSCP](https://winscp.net/)

### 📚 Documentation

* [VirtualBox Documentation](https://virtualbox.org/manual)
* [Kali Linux Documentation](https://kali.org/docs)
* [Debian Network Configuration](https://wiki.debian.org/NetworkConfiguration)
* [SANS Cybersecurity Resources](https://www.sans.org/)

---

# 🎓 Weekly Learning Summary

## 📅 Week 1 — Setup & Configuration

During the first week, the following tasks were completed:

* ✅ Understood virtualization fundamentals
* ✅ Configured an isolated cybersecurity lab
* ✅ Practiced IP networking concepts
* ✅ Configured Kali Linux
* ✅ Practiced VM management
* ✅ Documented the complete setup process

## 💡 Skills Developed

| Category            | Skills                                              |
| ------------------- | --------------------------------------------------- |
| **Technical**       | VirtualBox, Kali Linux, networking, troubleshooting |
| **Security**        | Network isolation, sandboxing, controlled testing   |
| **Documentation**   | Technical documentation and configuration tracking  |
| **Problem Solving** | Systematic troubleshooting                          |

---

# 🚀 Next Steps

The next phase of the project will focus on expanding the cybersecurity lab.

* 🔍 Install common penetration testing tools
* 🌐 Configure additional virtual machines
* 🛡️ Practice Nmap in a controlled environment
* 🧪 Practice Metasploit in an authorized lab
* 💻 Deploy intentionally vulnerable machines
* 🔐 Perform controlled security testing
* 📊 Explore network monitoring and analysis

---

# 👤 Author Information

| 👤 Field        | 📝 Details            |
| --------------- | --------------------- |
| **Name**        | Your Full Name        |
| **Student ID**  | Your Student ID       |
| **Batch**       | Your Batch / Year     |
| **Program**     | Your Program          |
| **Institution** | Your Institution      |
| **Email**       | Your Email            |
| **GitHub**      | Your GitHub Profile   |
| **LinkedIn**    | Your LinkedIn Profile |
| **Portfolio**   | Your Portfolio        |

## 🤝 Connect With Me

* 🐙 **GitHub:** [@yourusername](https://github.com/yourusername)
* 💼 **LinkedIn:** [Your LinkedIn](https://linkedin.com/in/your-profile)
* 🐦 **Twitter/X:** [@yourhandle](https://twitter.com/yourhandle)

---

# ⚠️ Warning & Disclaimer

> ## 🔐 Educational Use Only
>
> This cybersecurity laboratory is strictly intended for **educational and authorized security testing purposes**.
>
> * ✅ Only test systems you own or have permission to test
> * ✅ Follow ethical hacking guidelines
> * ✅ Follow applicable laws and regulations
> * ❌ Never use these techniques for unauthorized access
> * ❌ Never target production systems without authorization

---

# 💡 Security Best Practices

1. 🔄 Always revert to a clean snapshot before new experiments.
2. 🔑 Change the default Kali password immediately.
3. 🔄 Keep the system updated.

```bash
sudo apt update && sudo apt upgrade
```

4. 🛡️ Keep the host system and VM security software updated.
5. 📝 Document every configuration change.
6. 💾 Maintain regular backups.
7. 🔐 Never store sensitive credentials inside the lab VM.
8. 🌐 Keep security testing within authorized environments.

---

# 🎥 Video Demonstration

## 📹 Lab Walkthrough

**Duration:** 30–60 seconds

The demonstration includes:

* VM boot sequence
* Kali Linux login
* Network verification
* Snapshot management
* System information
* Lab environment overview

📹 **[Watch Lab Demonstration](https://videos/lab_demo.mp4)**

> ⚠️ Replace the placeholder video URL with the actual video link before publishing.

---

# 📊 Project Status

| 🧩 Project Phase        | 📌 Status   | 📅 Date |
| ----------------------- | ----------- | ------- |
| VirtualBox Installation | ✅ Completed | [Date]  |
| NAT Network Setup       | ✅ Completed | [Date]  |
| Kali VM Deployment      | ✅ Completed | [Date]  |
| IP Configuration        | ✅ Completed | [Date]  |
| Snapshot Creation       | ✅ Completed | [Date]  |
| Testing & Verification  | ✅ Completed | [Date]  |
| Documentation           | ✅ Completed | [Date]  |
| Video Demonstration     | ✅ Completed | [Date]  |

---

# 🤝 Contributing

Contributions and improvements are welcome.

### 🔧 How to Contribute

```bash
# Fork the repository

# Clone your fork
git clone <your-repository-url>

# Create a feature branch
git checkout -b feature/AmazingFeature

# Commit your changes
git commit -m "Add some AmazingFeature"

# Push the branch
git push origin feature/AmazingFeature
```

Then open a **Pull Request** on GitHub.

---

# 📄 License

> This project is created for **educational purposes only**.
>
> * Not intended for malicious use
> * Use responsibly and ethically
> * Follow all applicable laws and regulations
> * Always obtain proper authorization before security testing

---

# 🙏 Acknowledgments

Special thanks to:

* 🖥️ **Oracle** — VirtualBox
* 🐉 **Offensive Security** — Kali Linux
* 🌐 **Open-Source Community** — Tools and resources
* 👨‍🏫 **Instructors & Mentors** — Guidance and support

---

# 📞 Support

For questions, suggestions, or issues:

* 🐙 **GitHub Issues:** [Repository Issues](https://github.com/yourusername/yourrepo/issues)
* 📧 **Email:** Your Email
* 💬 **Discord:** [Your Discord Server](https://discord.gg/your-invite)

---

# 🏁 Conclusion

This project provides a **safe, isolated, and reproducible cybersecurity laboratory environment** using VirtualBox and Kali Linux.

Through this lab, practical experience was gained in:

**Virtualization → Networking → Linux Administration → Security Testing → Troubleshooting**

The combination of **network isolation, VM snapshots, backups, and systematic documentation** creates a reliable environment for continuous cybersecurity learning and experimentation.

---

<div align="center">

# 🔐 Learn • Practice • Secure • Repeat

**Cybersecurity Laboratory Environment**

</div>
