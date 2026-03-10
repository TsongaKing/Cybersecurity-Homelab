Cybersecurity Homelab
Overview

This repository documents my personal cybersecurity homelab used to practice penetration testing, security tooling, and Linux administration.

The lab environment was created using virtualization to simulate real-world security testing environments. It provides a safe platform to experiment with security tools, perform network enumeration, and analyze vulnerabilities.

The primary testing environment uses Kali Linux, a penetration testing distribution maintained by Offensive Security, running inside a virtual machine managed by Oracle VM VirtualBox.

Table of Contents

Overview

Homelab Architecture

Environment Configuration

Kali Linux System Preparation

Tools Installed and Practiced

Browser Configuration

System Organization

Lab Platforms Used

Typical Testing Workflow

Portfolio Project Description

Skills Demonstrated

Future Improvements

Author

Homelab Architecture
+--------------------------------------------------+
|                Host Computer (Windows)           |
|                                                  |
|  +--------------------------------------------+  |
|  |            VirtualBox Hypervisor           |  |
|  |                                            |  |
|  |   +------------------------------------+   |  |
|  |   |        Kali Linux Virtual Machine  |   |  |
|  |   |                                    |   |  |
|  |   |  Security Tools Installed:         |   |  |
|  |   |  - Nmap                            |   |  |
|  |   |  - Burp Suite                      |   |  |
|  |   |  - Gobuster                        |   |  |
|  |   |  - FFUF                            |   |  |
|  |   |  - Feroxbuster                     |   |  |
|  |   |  - LinPEAS / WinPEAS               |   |  |
|  |   |                                    |   |  |
|  |   +------------------------------------+   |  |
|  |                                            |  |
|  +--------------------------------------------+  |
|                                                  |
+--------------------------------------------------+

The hypervisor used is Oracle VM VirtualBox, which runs the penetration testing system Kali Linux.

Environment Configuration
Hypervisor

Virtualization platform: Oracle VM VirtualBox

Virtual Machine

Operating System: Kali Linux

System configuration:

RAM Allocation: ~8 GB

Swap: ~1 GB

CPU: Multiple cores assigned

Disk space expanded to support security tools and lab data

Example system memory output:

free -h

Example result:

Mem: total 7.6Gi
Used: ~902Mi
Available: ~6.7Gi
Swap: 953Mi

This configuration provides sufficient resources for security tools, browsers, and scanning utilities.

Kali Linux System Preparation

After installation, the system was updated and configured.

Typical update process:

sudo apt update
sudo apt upgrade

System dependencies and utilities were verified to ensure tools run correctly.

Tools Installed and Practiced
Network Scanning

Tool: Nmap

Example enumeration command:

nmap -sC -sV TARGET_IP

Purpose:

Identify open ports

Detect running services

Execute default vulnerability scripts

Web Application Security Testing

Tool: Burp Suite

Burp Suite is used to intercept and analyze HTTP/HTTPS traffic during web security testing.

Typical proxy configuration:

127.0.0.1:8080
Directory and Content Discovery

Tools used:

Gobuster

ffuf

Feroxbuster

Example directory discovery:

gobuster dir -u http://TARGET -w /usr/share/seclists/Discovery/Web-Content/common.txt
Wordlists

Wordlists used:

SecLists

Location:

/usr/share/seclists

These wordlists are used for:

directory discovery

fuzzing

password testing

Privilege Escalation Tools

Tools used:

LinPEAS

WinPEAS

These tools help identify privilege escalation opportunities on compromised systems.

Browser Configuration for Web Testing

Browser used:

Mozilla Firefox

Extension installed:

FoxyProxy

FoxyProxy enables quick switching between normal browsing and Burp Suite proxy interception.

System Organization

To keep the environment organized, directories were created for labs and tools.

Example structure:

labs/
tools/
wordlists/
reports/

This helps maintain clean lab documentation and separates scans, scripts, and results.

Lab Platforms Used

The homelab is used to practice cybersecurity exercises on:

TryHackMe

Hack The Box

These platforms provide intentionally vulnerable machines designed for security training.

Typical Testing Workflow
1. Perform Initial Reconnaissance
nmap -sC -sV TARGET_IP
2. Enumerate Web Directories
gobuster dir -u http://TARGET -w /usr/share/seclists/Discovery/Web-Content/common.txt
3. Intercept Traffic

Use Burp Suite proxy to capture requests.

4. Analyze Vulnerabilities

Review request/response behavior and identify potential weaknesses.

5. Privilege Escalation Enumeration

Run tools such as:

LinPEAS

WinPEAS

Portfolio Project Description

This homelab project demonstrates practical cybersecurity experience through the deployment and configuration of a virtual penetration testing environment.

The project simulates a real security testing workstation used for:

reconnaissance

vulnerability analysis

exploitation practice

Key areas demonstrated:

Virtualization

Deployment of virtual machines using Oracle VM VirtualBox to create an isolated testing environment.

Linux Administration

Configuration and management of Kali Linux including:

package updates

tool installation

system configuration

Security Tool Usage

Hands-on experience with commonly used penetration testing tools including:

Nmap

Burp Suite

Gobuster

ffuf

Feroxbuster

LinPEAS

WinPEAS

Skills Demonstrated

This project demonstrates practical skills in:

virtualization deployment

Linux system administration

penetration testing workflows

network enumeration

web application security testing

security tool configuration and usage

Future Improvements

Planned enhancements include:

additional vulnerable virtual machines

automated reconnaissance scripts

structured penetration testing reports

exploit development practice

Author

Phangasasa Muhlaba

Aspiring Cloud Security Engineer and DevSecOps professional focused on securing cloud infrastructure and developing hands-on cybersecurity skills.
