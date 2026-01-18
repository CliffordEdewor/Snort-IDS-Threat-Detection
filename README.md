# Real-Time Threat Detection and Mitigation Using Snort IDS

This project demonstrates the use of Snort Intrusion Detection System (IDS) for real-time detection and mitigation of cyber threats based on known vulnerabilities. It focuses on configuring Snort rules, monitoring network traffic, and responding to suspicious activities in a simulated environment.

## 🎯 Objectives
- Deploy and configure Snort IDS for real-time monitoring.  
- Detect and analyze malicious traffic using custom rules.  
- Mitigate detected threats through incident response measures.  
- Evaluate the effectiveness of Snort in protecting network infrastructure.

## 🖥️ Lab Environment & Requirements

This project was implemented in an isolated virtualised lab environment to safely simulate real-world attack and detection scenarios without impacting production systems.

### VirtualBox Lab Environment Overview
![VirtualBox Lab Overview](images/virtualbox-lab-environment-overview.png)

**Hardware**
- Host machine with Intel Core i5 or higher
- Minimum 8GB RAM (16GB recommended)
- Ethernet-capable NIC with packet capture support

**Virtual Machines**
- Snort IDS Machine: Ubuntu 20.04 LTS
- Attack Machine: Kali Linux

**Software & Tools**
- Oracle VM VirtualBox
- Snort IDS (v2.9.20)
- Wireshark
- Metasploit Framework

## 🧩 Project Architecture & Workflow

![Architecture Overview](images/architecture-overview.png)

*Figure: High-level architecture showing traffic flow and IDS monitoring.*

1. External traffic originates from an attacker machine.
2. Traffic passes through the internet, router, and firewall.
3. Snort IDS inspects packets in real time.
4. Suspicious activity triggers alerts to the administrator.
5. Legitimate traffic reaches internal hosts.

## ⚙️ Snort Configuration Overview

- Ubuntu 20.04 LTS was installed and configured as the IDS host.
- Snort 2.9.20 was compiled and installed with required dependencies.
- Custom detection rules were created and tuned.
- Snort was configured to generate real-time alerts and structured logs for threat detection and post-incident analysis.

Detailed installation steps are available in

[Snort Installation Guide](docs/snort-installation.md).

## ⚡ Key Features
- Packet inspection and rule-based intrusion detection  
- Real-time alerts on suspicious activities  
- Log analysis for forensic investigation  
- Integration with system/network defense measures

## 📊 Outcomes & Results
- Successfully detected simulated attack patterns such as port scans and suspicious payloads.
- Generated real-time alerts with tuned rules to reduce false positives.
- Demonstrated effective incident response through structured log analysis.
- The project demonstrates practical application of intrusion detection concepts aligned with real-world enterprise and academic security use cases. 

## 🔧 Technologies & Tools
- Snort IDS  
- Wireshark (traffic analysis)  
- Kali Linux / Ubuntu environments  
- Custom Snort rules  

## 📸 Implementation Evidence

### Snort Setup & Configuration Screen
![Snort Setup Configuration](images/snort-setup-configuration-screen.png)

### Snort Traffic Analysis Log 1
![Snort Traffic Analysis Log 1](images/snort-traffic-analysis-log-1.png)

### Snort Alert Log 2
![Snort Alert Log 2](images/snort-alert-log-2.png)

### Snort Alert Log 3
![Snort Alert Log 3](images/snort-alert-log-3.png)

## 📚 Use Case
This project was developed and successfully defended as a final-year academic project under the supervision of the **Computer Science Department, Petroleum Training Institute (PTI), Nigeria**, demonstrating the deployment of Snort IDS for real-time intrusion detection and network threat mitigation.

## 📄 License
This project is intended for educational demonstration, academic research, and portfolio presentation purposes.
