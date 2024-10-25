# Cybersecurity Home Lab Setup

This project provides a comprehensive guide to setting up a virtual cybersecurity home lab for hands-on experience with security tools, attack simulations, and incident response in a controlled environment.

## Table of Contents

1. [Overview](#overview)
2. [Lab Goals](#lab-goals)
3. [Hardware and Network Setup](#hardware-and-network-setup)
4. [Components and Configuration](#components-and-configuration)
   - [pfSense Configuration](#pfsense-configuration)
   - [Windows Server](#windows-server)
   - [Kali Linux](#kali-linux)
   - [SIEM Setup](#siem-setup)
5. [Lab Phases](#lab-phases)
6. [Future Enhancements](#future-enhancements)
7. [Resources and References](#resources-and-references)

---

## Overview

This lab setup includes virtual machines configured with security and network management tools to simulate real-world cybersecurity scenarios. The lab is ideal for practicing network monitoring, attack simulations, and incident response.

### Lab Goals

1. **Deploy SIEM**: Set up a SIEM to monitor and analyze security events.
2. **Simulate Network Attacks**: Conduct scans, exploit vulnerabilities, and test defenses.
3. **Incident Response**: Practice threat detection, isolation, and forensic analysis.
4. **Evaluate Security Tools**: Test firewall, IDS/IPS, and other security tools.

## Hardware and Network Setup

### Hardware

- **Host System**: Desktop with 32GB RAM, Ryzen 5600T processor, and 500GB+ storage.
- **Virtualization**: VMware Workstation to manage all virtual machines.

### Network Configuration

- **VMnet1 (Host-Only)**: IP range `192.168.170.0/24` for isolated lab network.
- **VMnet8 (NAT)**: IP range `192.168.11.0/24` for internet-connected VMs.

---

## Components and Configuration

### pfSense Configuration

- **Role**: Acts as the firewall and router to control traffic within the lab.
- **Configuration**:
  - **WAN Interface**: NAT connection through VMnet8 (`192.168.11.0/24`).
  - **LAN Interface**: Host-only network through VMnet1 (`192.168.170.0/24`).
  - **DHCP**: Enabled on LAN with IP range `192.168.170.10 - 192.168.170.100`.
- **Firewall Rules**: To be configured after Kali Linux setup to allow for attack simulations.

### Windows Server

- **Role**: Provides domain services, including Active Directory, DNS, and DHCP.
- **Installation**: 
  - Installed Windows Server 2022 in Minimal Server Interface mode.
  - Configured as a domain controller for `lab.local`.
  - Initial setup done via Sconfig for basic network and hostname setup.

### Kali Linux

- **Role**: Primary attack machine for penetration testing and vulnerability scanning.
- **Tools**: Includes Nmap for network scanning and Metasploit for exploit testing.

### SIEM Setup

- **Platform**: Ubuntu server as the SIEM server.
- **Tools**: Planning to use Splunk, OSSIM, or ELK Stack for monitoring and analysis.
- **Configuration**:
  - Logs to be collected from Windows Server, pfSense, and other VMs.
  - Setting up custom dashboards and alerts for real-time monitoring.

---

## Lab Phases

1. **Phase 1: SIEM Deployment** (1-2 weeks)
   - Deploy the SIEM server and configure log collection.

2. **Phase 2: Network Attack Simulation** (1-2 weeks)
   - Conduct scans, run exploits, and observe pfSense and SIEM defenses.

3. **Phase 3: Incident Response** (1-2 weeks)
   - Respond to incidents identified by SIEM and isolate affected machines.

4. **Phase 4: Firewall and IDS/IPS Testing** (1-2 weeks)
   - Configure and test pfSense rules and IDS/IPS with Snort or Suricata.

---

## Future Enhancements

- **Automated Incident Response**: Implement scripts for incident handling (e.g., PowerShell, Python).
- **Advanced Architectures**: Explore Zero Trust and cloud integration.
- **Additional Threat Scenarios**: Introduce advanced threats and remediation strategies.

---

## Resources and References

- [pfSense Documentation](https://docs.netgate.com/pfsense/en/latest/)
- [Microsoft Evaluation Center for Windows Server](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022)
- [Splunk Documentation](https://docs.splunk.com/)
- [Nmap Documentation](https://nmap.org/docs.html)

---

## Project Progress Tracking

- **Initial Setup**: All VMs installed, basic configurations done for pfSense, Windows Server.
- **Documentation**: Updated regularly to reflect new configurations and lessons learned.

