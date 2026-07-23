# Network Security Protocols and Configuration

## Overview

This lab focuses on implementing and configuring essential network security protocols used to protect data, authenticate users, and secure network communications. Practical exercises include configuring SSL/TLS on an Apache web server, securing remote access with SSH, implementing 802.1X network authentication, and deploying Snort as an Intrusion Detection System (IDS).

---

## Objectives

- Understand common network security protocols.
- Configure HTTPS using SSL/TLS on Apache.
- Secure remote administration using SSH.
- Implement 802.1X authentication with a RADIUS server.
- Install and configure Snort IDS.
- Monitor and analyze network traffic.

---

# Lab 1 – Understanding Network Security Protocols

## Objective

Study the purpose and importance of widely used network security protocols.

## Protocols Covered

### SSL/TLS

**Purpose**

- Encrypts data transmitted between clients and servers.
- Protects sensitive information during communication.

**Common Uses**

- HTTPS websites
- Online banking
- E-commerce
- Secure APIs

---

### IPsec

**Purpose**

- Secures IP communications using encryption and authentication.

**Common Uses**

- Virtual Private Networks (VPNs)
- Site-to-site communication
- Secure enterprise networking

---

### SSH (Secure Shell)

**Purpose**

- Provides encrypted remote access to Linux servers.
- Protects credentials and management traffic.

**Common Uses**

- Server administration
- Secure file transfer (SCP/SFTP)
- Remote command execution

---

### VPN (Virtual Private Network)

**Purpose**

- Creates encrypted tunnels across public networks.

**Benefits**

- Protects user privacy
- Encrypts Internet traffic
- Enables secure remote access
- Bypasses insecure public Wi-Fi

---

### IEEE 802.1X

**Purpose**

Port-based Network Access Control (PNAC)

**Benefits**

- Authenticates devices before granting network access
- Prevents unauthorized connections
- Integrates with RADIUS authentication

---

# Lab 2 – Configuring SSL/TLS on Apache

## Objective

Secure an Apache web server using SSL/TLS and redirect HTTP traffic to HTTPS.

## Tools Used

- Apache2
- OpenSSL
- Certbot (Let's Encrypt)

---

## Installation

```bash
sudo apt install apache2 -y
```

Enable SSL

```bash
sudo a2enmod ssl
```

Generate SSL Certificate

```bash
openssl req -new -x509 -days 365 -nodes -out server.crt -keyout server.key
```

Restart Apache

```bash
sudo systemctl restart apache2
```

---

## Tasks Performed

- Installed Apache2
- Generated SSL certificate
- Configured Virtual Hosts
- Enabled HTTPS (Port 443)
- Redirected HTTP (Port 80) to HTTPS
- Verified certificate installation

---

## Key Learning

SSL/TLS encrypts communication between clients and web servers, protecting sensitive information from interception.

---

## Screenshots

```
images/apache-installation.png

images/http-page.png

images/virtual-host-port80.png

images/virtual-host-port443.png

images/apache-ports.png

images/apache-restart.png

images/public-ip.png

images/http-to-https.png

images/ssl-certificate.png
```

---

# Lab 3 – Configuring SSH for Secure Remote Access

## Objective

Secure Linux remote administration using SSH.

## Installation

```bash
sudo apt install openssh-server
```

Start SSH

```bash
sudo systemctl start ssh
```

Check Status

```bash
sudo systemctl status ssh
```

---

## Security Hardening

The following changes were implemented:

- Changed default SSH port from **22** to **2222**
- Disabled root login
- Enabled public key authentication
- Disabled password authentication (where applicable)

---

## Benefits

- Encrypted remote administration
- Reduced brute-force attacks
- Strong authentication
- Secure server management

---

## Screenshot

```
images/ssh-installation.png
```

---

# Lab 4 – Implementing IEEE 802.1X Authentication

## Objective

Configure network access control using an AAA RADIUS server.

---

## Environment

- Cisco Packet Tracer
- Router
- Switch
- AAA Server
- Client Devices

---

## Configuration Summary

- Configured AAA authentication
- Added RADIUS server
- Configured local backup authentication
- Verified authenticated users
- Tested successful and failed logins

---

## Key Concepts

802.1X ensures:

- Device authentication
- User authentication
- Secure network access
- Protection against unauthorized devices

---

## Screenshots

```
images/radius-server.png

images/router-authentication.png

images/local-user.png

images/aaa-configuration.png

images/client-authentication.png
```

---

# Lab 5 – Intrusion Detection using Snort IDS

## Objective

Install and configure Snort to monitor network traffic.

---

## Installation

```bash
sudo apt-get install snort
```

or

```bash
sudo apt-get install snort -y
```

---

## Configuration

Edit Snort configuration

```bash
sudo nano /etc/snort/snort.conf
```

Configure HOME_NET

```text
HOME_NET 192.168.x.x
```

---

## Run Snort

```bash
sudo snort -A console -c /etc/snort/snort.conf -i eth0
```

---

## Learning Outcomes

Snort was configured to:

- Monitor network traffic
- Detect suspicious activities
- Generate alerts
- Analyze packets in real time

---

## Screenshot

```
images/snort-installation.png

images/snort-configuration.png

images/snort-monitoring.png
```

---

# Skills Demonstrated

- Network Security
- SSL/TLS
- Apache Web Server
- HTTPS Configuration
- OpenSSL
- SSH Hardening
- Linux Administration
- AAA Authentication
- RADIUS Server
- IEEE 802.1X
- Snort IDS
- Network Monitoring

---

# Tools Used

- Kali Linux
- Apache2
- OpenSSL
- OpenSSH
- Cisco Packet Tracer
- RADIUS Server
- Snort IDS
- Linux Terminal

---

# Learning Outcomes

By completing this lab, I gained practical experience in:

- Implementing secure communication using SSL/TLS.
- Hardening SSH for secure remote administration.
- Configuring 802.1X network authentication.
- Deploying and configuring Snort IDS.
- Monitoring network traffic for security events.
- Applying network security best practices in Linux environments.

---

# Repository Structure

```
Network-Security-Protocols-and-Configuration/
│
├── README.md
├── report.pdf
└── images/
    ├── apache-installation.png
    ├── http-page.png
    ├── virtual-host-port80.png
    ├── virtual-host-port443.png
    ├── apache-ports.png
    ├── apache-restart.png
    ├── public-ip.png
    ├── http-to-https.png
    ├── ssl-certificate.png
    ├── ssh-installation.png
    ├── radius-server.png
    ├── router-authentication.png
    ├── local-user.png
    ├── aaa-configuration.png
    ├── client-authentication.png
    ├── snort-installation.png
    ├── snort-configuration.png
    └── snort-monitoring.png
```

---

## Author

**Ayilara Busari Dare**

- Cybersecurity Analyst
- SOC Analyst
- Linux Security Enthusiast
- Network Security Researcher

---
