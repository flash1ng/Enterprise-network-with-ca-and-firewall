🏢 Enterprise Network with Certificate Authority and Firewall
📌 Project Overview

This project represents a simulated enterprise network built in Cisco Packet Tracer with:

VLAN segmentation

Centralized Certificate Authority

FTP server configuration

Firewall implementation using iptables

Guest Wi-Fi network

Inter-VLAN routing

The goal was to design a secure corporate network infrastructure following basic enterprise security principles.

🖥 Network Architecture

The company consists of 20 PCs divided into four departments:

Department	VLAN	Name
IT	10	IT
HR	20	Persona
Sales	30	Sales
Office	40	SkillBox

✔ Each department is isolated using VLAN
✔ All devices can communicate (correct routing configured)
✔ Server located in IT department

🔐 Services Implemented
1️⃣ FTP Server

Configured on the IT server

Provides file access for employees

Supports internal update distribution

2️⃣ Certificate Authority (Ubuntu, VirtualBox)

Created:

Root CA (mycaroot.crt)

IT certificate

Persona certificate

Sales certificate

SkillBox certificate

Each VLAN has its own certificate for secure internal services.

🔥 Firewall Configuration

Firewall deployed on Ubuntu server using iptables.

Key features:

Traffic forwarding enabled

Packet filtering between VLANs

Custom security rules

Example rules:

iptables -A FORWARD -i eth0 -o eth1 -j ACCEPT
iptables -A FORWARD -p tcp --dport 21 -j ACCEPT
iptables -A FORWARD -j DROP
🌐 Guest Network

Separate Wi-Fi network

Internet access only

No internal network protection required

🛠 Technologies Used

Cisco Packet Tracer

Ubuntu (VirtualBox)

OpenSSL (for CA)

iptables

FTP service

📂 Repository Structure

enterprise-network-with-ca-and-firewall/
│
├── Cisco_Packet_Tracer/
│   └── Final.pkt
│
├── Certificates/
│   ├── mycaroot.crt
│   ├── it_cert.crt
│   ├── persona_cert.crt
│   └── company_cert.crt
│
├── Firewall/│
│   └── rules_screenshot.jpg
│
└── README.md

🎯 Learning Outcomes

VLAN configuration

Inter-VLAN routing

Linux firewall configuration

Certificate Authority setup

Network segmentation

Basic enterprise network security design
