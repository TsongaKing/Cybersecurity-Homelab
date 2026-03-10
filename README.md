# Cybersecurity Homelab

![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kali-linux&logoColor=white)
![VirtualBox](https://img.shields.io/badge/VirtualBox-183A61?style=for-the-badge&logo=virtualbox&logoColor=white)
![Burp Suite](https://img.shields.io/badge/Burp_Suite-FF6633?style=for-the-badge&logo=burp-suite&logoColor=white)
![Nmap](https://img.shields.io/badge/Nmap-0E83CD?style=for-the-badge&logo=nmap&logoColor=white)

## 📋 Overview

This repository documents my personal cybersecurity homelab used to practice penetration testing, security tooling, and Linux administration.

The lab environment was created using virtualization to simulate real-world security testing environments. It provides a safe platform to experiment with security tools, perform network enumeration, and analyze vulnerabilities.

The primary testing environment uses **Kali Linux**, a penetration testing distribution maintained by Offensive Security, running inside a virtual machine managed by **Oracle VM VirtualBox**.

## 📑 Table of Contents

- [Overview](#-overview)
- [Homelab Architecture](#-homelab-architecture)
- [Environment Configuration](#-environment-configuration)
- [Kali Linux System Preparation](#-kali-linux-system-preparation)
- [Tools Installed and Practiced](#-tools-installed-and-practiced)
- [Browser Configuration](#-browser-configuration)
- [System Organization](#-system-organization)
- [Lab Platforms Used](#-lab-platforms-used)
- [Typical Testing Workflow](#-typical-testing-workflow)
- [Portfolio Project Description](#-portfolio-project-description)
- [Skills Demonstrated](#-skills-demonstrated)
- [Future Improvements](#-future-improvements)
- [Author](#-author)

## 🏗️ Homelab Architecture
┌─────────────────────────────────────────────────────────────┐
│ Host Computer (Windows) │
│ │
│ ┌──────────────────────────────────────────────────────┐ │
│ │ VirtualBox Hypervisor │ │
│ │ │ │
│ │ ┌──────────────────────────────────────────────┐ │ │
│ │ │ Kali Linux Virtual Machine │ │ │
│ │ │ │ │ │
│ │ │ ⚡ Security Tools Installed: │ │ │
│ │ │ • Nmap │ │ │
│ │ │ • Burp Suite │ │ │
│ │ │ • Gobuster │ │ │
│ │ │ • FFUF │ │ │
│ │ │ • Feroxbuster │ │ │
│ │ │ • LinPEAS / WinPEAS │ │ │
│ │ │ │ │ │
│ │ └──────────────────────────────────────────────┘ │ │
│ │ │ │
│ └──────────────────────────────────────────────────────┘ │
│ │
└─────────────────────────────────────────────────────────────┘

text

## ⚙️ Environment Configuration

### Hypervisor
- **Virtualization platform:** Oracle VM VirtualBox

### Virtual Machine Specifications
| Component | Configuration |
|-----------|--------------|
| **OS** | Kali Linux |
| **RAM** | ~8 GB |
| **Swap** | ~1 GB |
| **CPU** | Multiple cores assigned |
| **Storage** | Expanded disk space for tools and data |

#### System Memory Output Example
```bash
$ free -h
              total        used        free      shared  buff/cache   available
Mem:           7.6Gi       902Mi       5.8Gi        23Mi       953Mi       6.7Gi
Swap:          953Mi          0B       953Mi
This configuration provides sufficient resources for security tools, browsers, and scanning utilities.

🔧 Kali Linux System Preparation
After installation, the system was updated and configured:

bash
# Update package repositories
sudo apt update

# Upgrade installed packages
sudo apt upgrade -y

# Verify system dependencies
sudo apt install -y build-essential

🛠️ Tools Installed and Practiced

Network Scanning
Tool	Purpose	Example Usage
Nmap	Port scanning & service detection	nmap -sC -sV TARGET_IP

Web Application Security Testing
Tool	Purpose
Burp Suite	Intercept and analyze HTTP/HTTPS traffic
Proxy Config	127.0.0.1:8080

Directory and Content Discovery
Tool	Description	Example
Gobuster	Directory/file enumeration	gobuster dir -u http://TARGET -w /usr/share/seclists/Discovery/Web-Content/common.txt
FFUF	Fuzzing tool	ffuf -u http://TARGET/FUZZ -w /usr/share/seclists/Discovery/Web-Content/common.txt
Feroxbuster	Recursive content discovery	feroxbuster -u http://TARGET -w /usr/share/seclists/Discovery/Web-Content/common.txt

Wordlists
SecLists - Location: /usr/share/seclists
Directory discovery
Fuzzing
Password testing

Privilege Escalation Tools
Tool	Purpose
LinPEAS	Linux privilege escalation enumeration
WinPEAS	Windows privilege escalation enumeration

🌐 Browser Configuration for Web Testing
Browser: Mozilla Firefox
Extension: FoxyProxy
Enables quick switching between normal browsing and Burp Suite proxy interception

📁 System Organization
To maintain a clean environment, the following directory structure was created:

text
labs/
├── tryhackme/
├── hackthebox/
tools/
├── enumeration/
├── exploitation/
wordlists/
├── custom/
├── seclists/
reports/
├── scans/
├── findings/

🎯 Lab Platforms Used
The homelab is used to practice cybersecurity exercises on:

TryHackMe - Beginner-friendly rooms and guided learning
Hack The Box - Advanced machines and challenges

🔄 Typical Testing Workflow
1. Perform Initial Reconnaissance
bash
nmap -sC -sV TARGET_IP

2. Enumerate Web Directories
bash
gobuster dir -u http://TARGET -w /usr/share/seclists/Discovery/Web-Content/common.txt

3. Intercept Traffic
Configure Burp Suite proxy
Enable FoxyProxy in Firefox
Capture and analyze requests

4. Analyze Vulnerabilities
Review request/response behavior
Identify potential weaknesses
Test for common vulnerabilities

5. Privilege Escalation Enumeration
bash
# On Linux targets
./linpeas.sh

# On Windows targets
.\winpeas.exe

📝 Portfolio Project Description
This homelab project demonstrates practical cybersecurity experience through the deployment and configuration of a virtual penetration testing environment.

The project simulates a real security testing workstation used for:

🔍 Reconnaissance
🕵️ Vulnerability analysis
💻 Exploitation practice

Key Areas Demonstrated

Virtualization
Deployment of virtual machines using Oracle VM VirtualBox
Creation of isolated testing environments
Resource allocation and optimization

Linux Administration
Configuration and management of Kali Linux
Package management and updates
System configuration and optimization
Directory structure organization

Security Tool Usage
Hands-on experience with industry-standard tools:
Nmap - Network mapping and service detection
Burp Suite - Web application security testing
Gobuster/FFUF/Feroxbuster - Content discovery
LinPEAS/WinPEAS - Privilege escalation enumeration

🏆 Skills Demonstrated
This project demonstrates practical skills in:

Skill Area	Specific Competencies
Virtualization	VM deployment, resource management, snapshot creation
Linux Administration	CLI proficiency, package management, system configuration
Penetration Testing	Reconnaissance, enumeration, vulnerability analysis
Network Security	Port scanning, service detection, network mapping
Web Security	Traffic interception, directory enumeration, fuzzing
Tool Configuration	Security tool installation and optimization

🚀 Future Improvements
Planned enhancements for the homelab:

Additional vulnerable virtual machines
Set up Metasploitable 3
Deploy DVWA (Damn Vulnerable Web Application)
Configure Active Directory lab environment

Automated reconnaissance scripts
Create bash scripts for automated scanning
Develop enumeration workflows

Structured penetration testing reports
Implement report templates
Document findings and remediation steps

Exploit development practice
Binary exploitation exercises
Buffer overflow challenges

👤 Author
Phangasasa Muhlaba

Aspiring Cloud Security Engineer and DevSecOps professional focused on securing
cloud infrastructure and developing hands-on cybersecurity skills.
