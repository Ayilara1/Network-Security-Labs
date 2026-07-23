# Simulating Network Routing and VLAN Configuration in Linux

## Overview

This lab demonstrates how Linux can be used to simulate enterprise networking concepts, including:

- Static Routing
- VLAN Segmentation using Network Namespaces
- IP Address Assignment and Subnetting
- Connectivity Testing with Ping and Traceroute
- Firewall Configuration using iptables
- Traffic Monitoring using tcpdump

These practical exercises provide hands-on experience with Linux networking, routing, firewall configuration, and network troubleshooting.

---

## Objectives

- Configure static routes on Linux.
- Simulate VLANs using Linux network namespaces.
- Assign IP addresses and implement subnetting.
- Test connectivity using Ping and Traceroute.
- Configure firewall and routing rules using iptables.
- Monitor and analyze network traffic using tcpdump.

---

# Lab 1 – Static Routing

## Objective

Configure static routes to allow communication between the Linux machine and the OWASP Broken Web Application VM.

### Commands Used

```bash
sudo ip route add 192.168.92.0/24 via 10.0.2.2 dev eth0

ip route show

ping <OWASP_VM_IP>
```

### Explanation

Static routing allows administrators to manually define network paths instead of relying on dynamic routing protocols.

Advantages include:

- Predictable routing
- Better control
- Reduced routing overhead

Challenges include:

- Configuration errors
- Gateway failures
- Routing loops
- Difficult scalability
- Manual maintenance

---

## Screenshot

```
images/static-routing.png
```

---

# Lab 2 – VLAN Simulation Using Network Namespaces

## Objective

Create isolated virtual networks using Linux Network Namespaces.

### Commands

```bash
sudo ip netns add vlan1

sudo ip netns add vlan2

sudo ip link add veth1 type veth peer name veth2

sudo ip link set veth1 netns vlan1

sudo ip link set veth2 netns vlan2

sudo ip netns exec vlan1 ip addr add 192.168.10.1/24 dev veth1

sudo ip netns exec vlan1 ip link set lo up
```

### Benefits

- Complete network isolation
- Lightweight virtualization
- Ideal for Docker and Kubernetes
- Secure multi-tenant networking
- Easy testing of network topologies

---

## Screenshot

```
images/network-namespaces.png
```

---

# Lab 3 – IP Address Assignment and Subnetting

## Objective

Configure subnetting and assign IP addresses to Linux namespaces.

### Commands

```bash
ip addr add 192.168.10.1/24 dev veth1

ip route add 192.168.20.0/24 via 192.168.10.254
```

### Learning Outcomes

Subnetting improves:

- Network organization
- Efficient IP allocation
- Reduced broadcast traffic
- Improved security

Common challenges include:

- IP conflicts
- Manual configuration errors
- Scalability

---

## Screenshot

```
images/ip-subnetting.png
```

---

# Lab 4 – Connectivity Testing

## Objective

Verify communication using Ping and Traceroute.

### Commands

```bash
ping 192.168.20.1

traceroute 192.168.20.1
```

### Findings

Traceroute helps identify:

- Routing paths
- Packet loss
- High latency
- Network bottlenecks

---

## Screenshot

```
images/ping-traceroute.png
```

---

# Lab 5 – Firewall Configuration using iptables

## Objective

Configure Linux as a firewall and router.

### Commands

Enable IP Forwarding

```bash
echo 1 > /proc/sys/net/ipv4/ip_forward
```

Allow forwarding

```bash
sudo iptables -A FORWARD -s 192.168.10.0/24 -d 192.168.20.0/24 -j ACCEPT
```

Block traffic

```bash
sudo iptables -A FORWARD -s 192.168.10.0/24 -j DROP
```

### Key Concepts

iptables allows administrators to:

- Filter traffic
- Perform packet forwarding
- Implement firewall rules
- Control network access

Common mistakes include:

- Incorrect rule order
- Overly permissive rules
- Excessive rule complexity

---

## Screenshot

```
images/iptables-rules.png
```

---

# Lab 6 – Network Traffic Monitoring

## Objective

Capture and analyze network traffic using tcpdump.

### Commands

```bash
sudo tcpdump -i veth1

sudo tcpdump -i eth0
```

### Traffic Observed

- TCP
- HTTP
- ACK packets
- Sequence numbers

### Benefits

tcpdump helps:

- Troubleshoot connectivity
- Detect packet loss
- Analyze protocols
- Investigate suspicious traffic

---

## Screenshot

```
images/tcpdump.png
```

---

# Skills Demonstrated

- Linux Networking
- Static Routing
- VLAN Simulation
- Linux Network Namespaces
- IP Subnetting
- Network Troubleshooting
- Ping & Traceroute
- iptables Firewall
- TCP/IP
- Packet Capture
- tcpdump
- Linux Administration

---

# Tools Used

- Kali Linux
- Linux Network Namespaces
- iproute2
- iptables
- tcpdump
- Ping
- Traceroute
- OWASP Broken Web Applications VM

---

# Learning Outcomes

After completing this lab, I successfully learned how to:

- Configure static routes.
- Build isolated virtual networks using namespaces.
- Assign IP addresses and perform subnetting.
- Configure Linux firewall rules.
- Monitor network traffic using tcpdump.
- Troubleshoot routing and connectivity issues.

---

## Repository Structure

```
Simulating-Network-Routing-and-VLAN-Configuration/
│
├── README.md
├── report.pdf
├── images/
│   ├── static-routing.png
│   ├── network-namespaces.png
│   ├── ip-subnetting.png
│   ├── ping-traceroute.png
│   ├── iptables-rules.png
│   └── tcpdump.png
```

---

## Author

**Ayilara Busari Dare**

- Cybersecurity Analyst
- SOC Analyst
- Linux Security Enthusiast
- Network Security Researcher

---
