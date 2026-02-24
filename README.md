# 🏢 Enterprise Network Infrastructure with PKI and Firewall Segmentation

## 📌 Project Overview

This project demonstrates the design and implementation of a segmented enterprise network with centralized security services.

The infrastructure was built in **Cisco Packet Tracer**, with security components deployed on **Ubuntu (VirtualBox)**.

The main objective was to simulate a secure corporate environment using:

* VLAN-based segmentation
* Inter-VLAN routing
* Centralized Certificate Authority (PKI)
* Linux-based firewall (iptables)
* FTP service for internal distribution
* Isolated guest Wi-Fi network

The project focuses on applying enterprise security principles such as segmentation, traffic filtering, and trust management.

---

# 🏗 Architecture Overview

## Network Scale

* 20 Workstations
* 4 Departments
* 1 Internal Server
* 1 Firewall (Linux-based)
* 1 Guest Wi-Fi segment

---

## VLAN Segmentation

| Department | VLAN ID | Purpose                  |
| ---------- | ------- | ------------------------ |
| IT         | 10      | Infrastructure & Updates |
| HR         | 20      | Personnel Systems        |
| Sales      | 30      | Sales Operations         |
| Office     | 40      | Corporate Workspace      |

### Design Principles

* Logical isolation between departments
* Broadcast domain separation
* Reduced attack surface
* Controlled inter-VLAN routing

All VLANs are routed via Layer 3 configuration, ensuring full connectivity while maintaining segmentation.

---

# 🌐 IP Addressing Strategy


| VLAN    | Subnet          |
| ------- | --------------- |
| VLAN 10 | 192.168.10.0/24 |
| VLAN 20 | 192.168.20.0/24 |
| VLAN 30 | 192.168.30.0/24 |
| VLAN 40 | 192.168.40.0/24 |

Gateway for each VLAN configured on the routing device.

---

# 🔐 Public Key Infrastructure (PKI)

A centralized Certificate Authority was deployed on Ubuntu using OpenSSL.

## PKI Hierarchy

Root CA:

* `mycaroot.crt`

Issued Certificates:

* `it_cert.crt`
* `persona_cert.crt`
* `sales_cert.crt`
* `Company_cert.crt`

## Security Objectives

* Establish trust inside internal infrastructure
* Enable secure service validation
* Simulate enterprise-level certificate lifecycle

Each department logically corresponds to its own certificate for service-level authentication.

---

# 📂 FTP Service (Internal Distribution Server)

The FTP service is hosted inside VLAN 10 (IT Department).

### Purpose

* Internal update distribution
* Centralized file access
* Controlled service exposure

Port 21 explicitly allowed through firewall rules.

---

# 🔥 Firewall Architecture (iptables)

Firewall implemented on Ubuntu with dual network interfaces:

* `eth0` – Internal corporate network
* `eth1` – External / uplink





## Firewall Logic Explanation

1. Allow internal outbound traffic
2. Allow FTP traffic explicitly
3. Drop all other forwarded traffic (default deny approach)

### Security Model

* Explicit allow
* Implicit deny
* Service-level filtering
* Segmented traffic control

This mimics enterprise perimeter firewall behavior.

---

# 🌐 Guest Wi-Fi Network

The guest segment is logically separated from internal VLANs.

### Characteristics

* Internet access only
* No access to corporate VLANs
* No internal trust relationships

Designed to simulate BYOD / visitor network policies.

---

# 🛠 Technologies Used

* Cisco Packet Tracer
* Ubuntu (VirtualBox)
* OpenSSL
* iptables
* VLAN configuration
* Inter-VLAN routing
* FTP service deployment

---

# 📊 Security Considerations

This project demonstrates several enterprise security principles:

* Network segmentation reduces lateral movement risk
* VLAN isolation limits broadcast domains
* Firewall filtering enforces traffic policy
* PKI provides internal trust framework
* Service exposure minimized and controlled

Potential improvements for production-level design:

* Stateful firewall rules
* Logging and monitoring
* IDS/IPS integration
* Certificate revocation list (CRL)
* VPN remote access
* DMZ segmentation

---

# 📂 Repository Structure

```
enterprise-network-with-ca-and-firewall/
│
├── Cisco_Packet_Tracer/
│   └── Final.pkt
│
├── Certificates/
│   ├── mycaroot.crt
│   ├── it_cert.crt
│   ├── persona_cert.crt│  
│   └── skillbox_cert.crt
│
├── Firewall/  
│   └── rules_screenshot.jpg
│
└── README.md
```

---

# 🎯 Engineering Outcomes

Through this project I demonstrated practical skills in:

* Enterprise network segmentation
* Layer 2 / Layer 3 configuration
* Linux-based firewall deployment
* PKI infrastructure setup
* Controlled service exposure
* Secure network design principles

---

# 🧠 What This Project Represents

This lab simulates a small-scale enterprise infrastructure with applied network security controls and centralized trust management.

It reflects practical understanding of:

* Network isolation
* Access control
* Traffic filtering
* Secure service deployment
* Infrastructure design thinking

---


