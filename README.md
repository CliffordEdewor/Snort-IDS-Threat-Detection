# Engineering a Snort IDS for Threat Detection and Security Monitoring

This repository documents the design, implementation, and validation of a Snort-based intrusion detection environment for real-time threat monitoring, attack detection, and security alerting within a virtualised network.

## 🛡️ Security Monitoring Capabilities
- Deploy and configure a Snort IDS sensor for real-time traffic inspection.  
- Develop and tune custom detection rules for malicious traffic identification.
- Generate actionable alerts to support incident detection and response workflows.
- Evaluate the effectiveness of Snort in protecting network infrastructure.

## 🖥️ Deployment Environment

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

## 🧩 Detection Architecture

![Architecture Overview](images/architecture-overview.png)

*Figure: High-level architecture showing traffic flow and IDS monitoring.*

1. External traffic originates from an attacker machine.
2. Traffic passes through the internet, router, and firewall.
3. Snort IDS inspects packets in real time.
4. Suspicious activity triggers alerts to the administrator.
5. Legitimate traffic reaches internal hosts.

## 🎯 Threat Model

The objective of this lab was to evaluate how a Snort-based intrusion detection system identifies and alerts on common attack techniques within a controlled virtualised environment.

The following attack scenarios were planned and executed during testing.

| Attack Scenario | Objective | Detection Status |
|----------------|-----------|------------------|
| ICMP Reconnaissance | Verify basic network visibility | ✅ Detected |
| Port Scanning | Detect reconnaissance activity | ✅ Detected |
| SSH Authentication Attempts | Identify repeated login attempts | ✅ Detected |
| FTP Authentication Attempts | Detect insecure authentication activity | ✅ Detected |
| Suspicious TCP Traffic | Validate custom rule behaviour | ✅ Detected |

## 📐 Design Objectives

The project was designed to achieve the following objectives:
- Build a functional intrusion detection environment.
- Understand how network-based attacks are detected.
- Develop practical experience writing and tuning Snort rules.
- Validate alert generation using simulated attack traffic.
- Demonstrate detection engineering workflows that reflect real-world security operations.

## ⚙️ Snort Configuration Overview

- Ubuntu 20.04 LTS was installed and configured as the IDS host.
- Snort 2.9.20 was compiled and installed with required dependencies.
- Custom detection rules were created and tuned.
- Snort was configured to generate real-time alerts and structured logs for threat detection and post-incident analysis.

## 🛠 Detection Engineering

Rather than relying solely on default signatures, this implementation focused on understanding how Snort rules are created, tuned, and validated.

The detection process included:
- Developing and validating custom detection rules for representative attack scenarios.
- Validating rule behaviour using simulated attack traffic.
- Reviewing generated alerts to minimise false positives.
- Analysing captured logs to verify detection accuracy.
- Refining rule behaviour based on observed network traffic.

### Custom Detection Rule

The following custom rule was developed during testing to identify FTP authentication activity and validate real-time alert generation.

```snort
alert tcp any any -> any 21 (
    msg:"FTP Authentication Attempt";
    flow:to_server,established;
    content:"USER";
    sid:100003;
    rev:1;
)
```

Rather than relying only on the default Snort rules, I created this custom signature to detect FTP authentication attempts during testing. The rule was validated by generating FTP traffic from the attack machine and confirming that Snort produced the expected alerts.

Detailed installation steps are available in

[Snort Installation Guide](docs/snort-installation.md).

## ⚡ Key Features
- Packet inspection and rule-based intrusion detection  
- Real-time alerts on suspicious activities  
- Log analysis for forensic investigation  
- Integration with system/network defense measures

## 📈 Outcomes & Results
- Successfully detected simulated attack patterns such as port scans and suspicious payloads.
- Generated real-time alerts with tuned rules to reduce false positives.
- Validated detection and investigation workflows through structured alert and log analysis.
- The implementation demonstrates intrusion detection, monitoring, and alerting workflows aligned with enterprise security operations.

## 📊 Validation Summary

The deployment was validated through multiple simulated attack scenarios within the virtualised lab environment to confirm detection accuracy, alert generation, and log visibility.

| Validation Area | Outcome |
|-----------------|---------|
| Lab Environment | 4 Virtual Machines |
| IDS Platform | Snort 2.9.20 (Ubuntu 20.04 LTS) |
| Attack Scenarios | ICMP, SSH, FTP Authentication, Port Scanning |
| Detection Rules | Custom signatures validated alongside baseline Snort rules |
| Alert Generation | Real-time alerts successfully triggered |
| Traffic Analysis | Verified using Wireshark and Snort logs |
| Log Collection | Structured alerts generated for investigation |

## 🛡️ Operational Relevance
This implementation reflects practical security monitoring workflows commonly used in Security Operations Centres (SOC), including:
- Network intrusion detection
- Security monitoring and alerting
- Detection engineering and rule tuning
- Threat investigation and log analysis
- Incident response support

## 🏭 Industrial Security Relevance

Although this project was implemented within a controlled enterprise laboratory, the detection engineering principles demonstrated here are directly applicable to industrial and operational technology environments.

The same concepts are commonly used when monitoring segmented industrial networks, including:
- Network visibility
- Security monitoring
- Alert correlation
- Detection engineering
- Network segmentation
- Incident investigation

These capabilities support security operations across both traditional enterprise networks and critical infrastructure environments.

## 🔧 Security Stack
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

The validation process confirmed that the deployed IDS consistently detected representative attack patterns, generated structured alerts, and provided actionable logs suitable for investigation and security monitoring workflows.

## 📚 Use Case
This implementation demonstrates the deployment of a Snort-based intrusion detection solution for real-time network monitoring, attack detection, and alert generation within a controlled virtualised environment.

## 📘 Lessons Learned

Building an effective intrusion detection capability extends beyond installing security software.

This project reinforced the importance of:
- Understanding normal network behaviour before writing detection rules.
- Balancing detection coverage with false-positive reduction.
- Validating alerts using packet captures rather than assumptions.
- Documenting implementation decisions for repeatability.
- Designing security controls that support operational investigation rather than generating excessive alerts.

These lessons reflect practical detection engineering principles that are applicable across enterprise and industrial security environments.

## 📄 License
This repository is provided for cybersecurity learning, security monitoring demonstrations, and reference implementation purposes.
