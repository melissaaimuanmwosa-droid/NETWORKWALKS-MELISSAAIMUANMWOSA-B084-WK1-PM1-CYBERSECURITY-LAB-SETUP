# NETWORKWALKS-MELISSAAIMUANMWOSA-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP
# 🔐 Network Walks — Week 1

## Cybersecurity Lab Setup and Environment Configuration

> Building my foundation in cybersecurity through virtualization, Linux installation, network configuration, troubleshooting, and practical documentation.

---

## 🎯 1. Objectives

The objectives of this practical exercise were to:

- Create and configure a virtual machine using Oracle VirtualBox.
- Install and run Kali Linux in a virtual environment.
- Understand basic Linux terminal operations.
- Configure network connectivity using VirtualBox NAT.
- Learn how to manage network settings using NetworkManager.
- Troubleshoot IP addressing, gateway, and DNS resolution issues.
- Verify that the virtual machine has a working internet connection.

## 🧪 2. Purpose of the Lab

The purpose of this lab was to create a working Linux environment for cybersecurity practice.

Using virtualization, I was able to run Kali Linux on my Windows computer without installing it directly on my physical system.

This environment will serve as a foundation for future cybersecurity exercises, including networking, reconnaissance, vulnerability assessment, and ethical hacking.

## 🏗️ 3. Lab Architecture

The lab consists of a Windows host computer running Oracle VirtualBox, with Kali Linux operating as a guest virtual machine.

**Architecture overview:**

```text
             HOST COMPUTER
             Windows System
                   |
             Oracle VirtualBox
                   |
              Kali Linux VM
                   |
             Virtual Network
                   |
                NAT Mode
                   |
             Internet Access
```

**Architecture details:**

- Host machine: Windows
- Virtualization platform: Oracle VirtualBox
- Guest operating system: Kali Linux
- Network adapter: VirtualBox NAT
- Network interface: eth0
- Assigned IP address: `10.0.2.15`
- Default gateway: `10.0.2.2`

## ⚙️ 4. Lab Configuration

| Component | Configuration |
|---|---|
| Virtualization platform | Oracle VirtualBox |
| Virtual machine | Kali Linux |
| Guest operating system | Kali Linux |
| Network type | NAT |
| Network interface | eth0 |
| IPv4 address | `10.0.2.15/24` |
| Default gateway | `10.0.2.2` |
| IP assignment | DHCP |
| Network management | NetworkManager |

## 🛠️ 5. Setup Procedure

The lab setup involved the following stages:

### 1. Created a Virtual Machine

I used Oracle VirtualBox to create a virtual machine for Kali Linux.

I configured the virtual machine and attached the Kali Linux installation image.

### 2. Installed and Started Kali Linux

I installed and launched Kali Linux inside VirtualBox.

After installation, I explored the desktop environment and learned how to access the Linux terminal.

### 3. Configured Network Connectivity

I configured the network adapter to use NAT so that Kali Linux could access the internet through my host computer.

Initially, the network connection did not work as expected.

### 4. Investigated Network Issues

I used different Linux commands to identify the cause of the connection problems.

Some of the commands included:

**Checking network interfaces:**

```bash
ip -br addr
```

**Checking the routing table:**

```bash
ip route
```

**Checking network device status:**

```bash
nmcli device status
```

**Viewing network connections:**

```bash
nmcli connection show
```

These commands helped me identify the network interface, IP address, gateway, and connection configuration.

### 5. Corrected the IP Configuration

During troubleshooting, I discovered that my network connection was using a manually configured IP address instead of automatic DHCP.

The old configuration was:

- IP address: `10.0.0.2`
- Gateway: `10.0.0.1`
- IPv4 method: Manual

I changed the connection to automatic DHCP using:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.method auto
```

I also removed the old manually configured IP address and gateway settings.

After reconnecting the network interface, VirtualBox assigned a new IP address automatically.

### 6. Verified Network Connectivity

I used the following commands to test the connection.

**Testing connectivity using an IP address:**

```bash
ping -c 4 8.8.8.8
```

**Testing DNS resolution:**

```bash
ping -c 4 google.com
```

Both tests were successful, with zero packet loss.

My final network configuration was:

- IP address: `10.0.2.15`
- Default gateway: `10.0.2.2`
- Network interface: `eth0`
- IP assignment: DHCP

## ⚠️ 6. Challenges and Issues Encountered

During this exercise, I encountered several problems while setting up my virtual machine.

### 1. Kali Linux Display Resolution

The Kali Linux desktop initially appeared very small inside VirtualBox.

I attempted to fix it using Auto-resize Guest Display, Guest Additions, and Full-screen Mode, but these methods did not resolve the issue immediately.

### 2. Network Disconnection

Kali Linux initially displayed a network disconnection notification, and the `eth0` interface was disconnected.

I checked the network device status and attempted to reconnect the interface.

### 3. DNS Resolution Failure

When I tested the internet connection using:

```bash
ping -c 4 google.com
```

I received a temporary failure in name resolution error.

This showed that domain names were not resolving correctly.

### 4. Incorrect IP and Gateway Configuration

Further investigation revealed that my network connection was using a static IP address (`10.0.0.2`) and gateway (`10.0.0.1`).

These settings did not match the default VirtualBox NAT configuration.

I corrected this by changing the IPv4 method to automatic DHCP and removing the old static configuration.

### 5. Successful Troubleshooting

After reconnecting the network interface, Kali received the correct IP address and gateway.

I confirmed that both internet connectivity and DNS resolution were working successfully.

This experience taught me to investigate network problems systematically instead of repeatedly changing settings without understanding the cause.

## 💡 7. What I Learned

Through this practical exercise, I learned:

- How to create and configure virtual machines using Oracle VirtualBox.
- How to install and navigate Kali Linux.
- How to use the Linux terminal to perform basic system operations.
- How to identify network interfaces using Linux commands.
- The difference between static IP addressing and DHCP.
- How IP addresses, subnets, and default gateways work.
- How VirtualBox NAT provides internet access to virtual machines.
- How DNS translates domain names into IP addresses.
- How to use NetworkManager and `nmcli` to manage network connections.
- How to troubleshoot network connectivity problems.

Most importantly, I learned that cybersecurity requires patience, practical investigation, and the ability to solve technical problems.

## 🔍 8. Verification and Final Results

After completing the troubleshooting process, I verified that Kali Linux was connected successfully.

| Verification | Result |
|---|---|
| Kali Linux starts successfully | Successful |
| Network interface `eth0` | UP |
| IP address assignment | Successful |
| Default gateway | Configured |
| DHCP | Working |
| Ping to `8.8.8.8` | Successful |
| Ping to `google.com` | Successful |
| Packet loss | 0% |

**Final IP configuration:**

```text
Interface: eth0
IP Address: 10.0.2.15/24
Gateway: 10.0.2.2
Network Mode: NAT
```

## 🔗 9. Tools and Resources

- [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads) — Virtualization platform.
- [Kali Linux](https://www.kali.org/get-kali/) — Security-focused Linux distribution.
- [Kali Linux Documentation](https://www.kali.org/docs/) — Linux installation and configuration guidance.
- [NetworkManager Documentation](https://networkmanager.dev/docs/) — Network configuration and management.
- [GitHub](https://github.com/) — Project documentation and version control.

## 👩‍💻 10. About the Author

**Name:** Aimuanmwosa Melissa Osasere

**Program:** Networkwalks Cybersecurity Training

**Focus Areas:**
- Cybersecurity
- Ethical Hacking
- Linux

I am a cybersecurity learner interested in developing practical skills in ethical hacking, Linux, and network security.

I enjoy learning through hands-on exercises, solving technical problems, and documenting my progress as I develop my skills in the cybersecurity field.

## 📌 Project Information

- **Program:** Networkwalks Cybersecurity Training
- **Week:** 01
- **Project:** Cybersecurity Lab Setup
- **Platform:** GitHub
- **Environment:** Oracle VirtualBox and Kali Linux
- **Project Type:** Practical Cybersecurity Lab

---

## Conclusion

This first-week practical exercise gave me a better understanding of virtualization, Linux, and basic networking.

Although I encountered several challenges during the setup, I was able to investigate the problems, identify the incorrect network configuration, and restore internet connectivity.

I now have a working Kali Linux virtual environment that I can use for future cybersecurity practical exercises.

This is part of my continuous learning journey in cybersecurity through Networkwalks Cybersecurity Training.

**#Cybersecurity #EthicalHacking #KaliLinux #Linux #VirtualBox #Networking #NetworkWalks**
