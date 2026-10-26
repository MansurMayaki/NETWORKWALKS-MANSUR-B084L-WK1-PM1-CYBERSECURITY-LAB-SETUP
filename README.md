<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building an isolated virtual lab for penetration testing and ethical hacking practice**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Waqas%20Karim%20CCIE-C00000?style=flat-square" />
</p>

---

## 📌 Project Overview

This project focuses on setting up a **virtual cybersecurity and penetration-testing laboratory** using VirtualBox and Kali Linux.

The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly.

The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

---


## 🎯 Objectives

The main objectives of this project are to:

- Install and configure VirtualBox.
- Install/import Kali Linux as a virtual machine.
- Create a private **NAT Network** for the cybersecurity lab.
- Configure network connectivity for Kali Linux.
- Assign a consistent IP address to the Kali VM.
- Verify network connectivity and DNS resolution.
- Take a clean VM snapshot for recovery.
- Document the complete setup process.
- Prepare the environment for future cybersecurity projects.

---

## 🛡️ Purpose of the Lab

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Exploitation practice
- Security-tool experimentation

⚠️ **Important:** This laboratory must only be used for systems that you own or have explicit permission to test. Do not use the lab or its tools to attack unauthorized systems.

---

<img src="./Kali%20title.png" width="700">

## 🏗️ Lab Architecture

### 1. Kali Linux Home
<img src="./Kali%20Home.png" width="700">

Additional target machines can be added to the same virtual network in future projects.

---

## ⚙️ Lab Configuration

| 🧩 Component       | ⚙️ Configuration   |
| ------------------ | ------------------  |
| 🖥️ Host OS         | Kali Physical      |
| 🧠 Host RAM        | 16 GB               |
| ⚡ Processor       | Intel Core i7      |
| 🧰 Hypervisor      | VirtualBox 7.2  |
| 🐉 Security OS     | Kali Linux 2026.2  |
| 🧠 Kali RAM        | 2048 MB            |
| 🌐 Virtual Network | NAT Network        |
| 📡 Network Address | 10.0.0.0/24        |
| 🐧 Kali IP Address | 10.0.0.2/24        |
| 🚪 Default Gateway | 10.0.0.1           |
| 🌍 DNS Server      | 8.8.8.8            |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.99 |

---

# 🪜 Lab Setup Procedure


## Step 1. Install VirtualBox

VirtualBox was installed as the hypervisor.

---

## Step 2. Create the NAT Network

A dedicated NAT Network was created in VirtualBox.

Configuration:
Network Name: NatNetwork
IPv4 Prefix:  10.0.0.0/24
DHCP:         Enabled
IPv6:         Disabled

<img src="./Kali%20Network%20Settings.png" width="700">

A **NAT Network** was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.


---

## Step 4. Import Kali Linux

The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:

```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```
<img src="./Kali%20Settings%20Page.png" width="700">

The VM was allocated:

```text
RAM: 2048 MB
```



---

## Step 5. Configure the Kali Linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

<img src="./Kali%20VBox%20Network%20Settings%20SC.png" width="700">

---

## Step 6. Create a Clean VM Snapshot

After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:

```text
Clean Kali - Network Setup
```
<img src="./Kali%20Vbox%20MAchine.png" width="700">

The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.


---

# 🔎 Lab Verification

| ✅ Test                        | 🧾 Command                      | 🎯 Expected Result              |
| ----------------------------- | ------------------------------- | ------------------------------- |
| 🌐 Check IP address           | `ip a`                          | Correct Kali IP displayed       |
| 📡 Test gateway               | `ping 10.0.0.1`                 | Successful replies              |
| 🌍 Test Internet connectivity | `ping 8.8.8.8`                  | Successful replies              |
| 🔎 Test DNS resolution        | `nslookup networkwalks.com`     | Domain resolves                 |
| 🧰 Verify Nmap                | `nmap --version`                | Nmap version displayed          |
| 🔄 Verify snapshot            | Restore snapshot and run `ip a` | Baseline configuration restored |

### Example Results

```text
IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8
```

---


# Problems Encountered and Solutions

Documenting problems is an important part of the project. During the setup of the Cyber Security and Ethical Hacking lab, several configuration and access issues may arise while preparing the Kali Linux virtual machine and its networking environment.

## Problem 1. Distinguishing Physical Kali Linux from Virtual Kali Linux

My computer already had Kali Linux installed directly on the hardware (bare metal). However, the lab instructions required VirtualBox to create and configure a virtual machine.

This required distinguishing between the existing physical Kali installation and the separate Kali virtual machine used for the lab.

**Solution:**

1. Kept the existing bare-metal Kali Linux installation intact.
2. Installed VirtualBox to support virtual machine management.
3. Downloaded and opened the Kali Linux VirtualBox image.
4. Used the virtual machine for the VirtualBox-specific lab tasks.

This allowed me to retain my existing operating system while preparing a dedicated virtual environment for cybersecurity practice.

---

## Problem 2. Kali Linux Virtual Machine Login

After opening the Kali Linux virtual machine in VirtualBox, the system displayed a login screen requesting a username and password.

The login credentials depended on the type of Kali image downloaded.

**Solution:**

For the official pre-built Kali VirtualBox image, I attempted the default credentials:

- **Username:** `kali`
- **Password:** `kali`

If the credentials were rejected, the next step was to verify the image type and its associated login instructions.

---

## Problem 3. VirtualBox NAT Network Configuration

The lab instructions required a NAT Network using the `10.0.0.0/24` address range.

Configuring the virtual network correctly was necessary to provide the expected network connectivity between participating virtual machines.

**Solution:**

1. Opened VirtualBox's network settings.
2. Created a NAT Network.
3. Configured the network CIDR as `10.0.0.0/24`.
4. Enabled DHCP where required.
5. Connected the Kali virtual machine to the configured NAT Network.
6. Verified the VM's IP address and routing information.

The physical Kali host's network configuration was treated separately from the virtual network configuration.

---

## Problem 4. Capturing Screenshots for Lab Documentation

The lab required screenshots as evidence of the configuration and setup process. Since Kali Linux was also installed directly on the physical computer, it was important to distinguish screenshots of the host operating system from screenshots of the virtual machine.

**Solution:**

Used the Kali screenshot utility to capture relevant screens and terminal output.

```bash
xfce4-screenshooter
```

For network verification, the following commands were used:

```bash
ip addr
ip route
```

Screenshots were organised into a dedicated folder for easier documentation and submission.

---

# 💡 What I Learned

Through this project, I learned the importance of preparing a suitable virtual environment before performing cybersecurity and ethical hacking exercises.

### 1. Bare-Metal vs Virtualised Kali Linux

I learned the difference between running Kali Linux directly on physical hardware and running it as a virtual machine. I also learned that some lab tasks, such as taking VirtualBox snapshots, require a virtual machine.

### 2. VirtualBox and Virtual Machine Management

I learned how VirtualBox can be used to create, configure, start, and manage virtual machines for controlled cybersecurity practice.

### 3. Virtual Network Configuration

I learned the purpose of a NAT Network and how a virtual machine's network adapter, IP address, and routing configuration affect connectivity.

### 4. IP Address Verification

I learned how to use `ip addr` and `ip route` to inspect network interfaces, IP addressing, and routing information in Kali Linux.

### 5. Troubleshooting and Documentation

I learned the importance of investigating login issues, verifying configuration settings, documenting errors, and capturing screenshots as evidence of completed lab activities.

### 6. Virtual Machine Snapshots

I learned that snapshots provide recovery points for virtual machines and are useful before performing potentially disruptive lab exercises.

---

**Conclusion**

This lab strengthened my understanding of Kali Linux, virtualisation, network configuration, troubleshooting, and technical documentation. These skills provide a foundation for further practical cybersecurity and ethical hacking exercises.

# 🔐 Security & Ethical Use

This laboratory is intended strictly for education purposes only.

---

# 🔗 Tools & Resources


- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)

---

# 👤 Author

**Abdulmumin Mansur Mayaki**\
Cybersecurity Professional B084L

LinkedIn: [https://t.co/SZek9n4y8I](https://www.linkedin.com/in/mansur-abdulmumin-mayaki-01a78a437)

---

## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub
