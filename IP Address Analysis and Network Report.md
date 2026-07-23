# 🌐 Lab 5: IP Address Analysis and Network Report

**Course:** INT304 – Network Security and Protocols  # 🌐 Lab 5: IP Address Analysis and Network Report

**Network Security and Protocols**   
**Date:** 02/12/2024

---

# 📌 Objective

The purpose of this lab was to:

- Analyze public IP addresses of popular websites.
- Classify IP addresses into Classes A, B, and C.
- Understand reserved (private) IP address ranges.
- Calculate host capacity for different IP classes.
- Explore subnetting concepts.
- Perform network path analysis using Traceroute.
- Examine geographic information associated with public IP addresses.

---

# 🛠️ Tools Used

- Linux Terminal
- Ping
- Traceroute
- IPinfo.io
- GeoIP Lookup
- Web Browser

---

# Exercise 1 – Website IP Address Analysis

Ten popular websites were selected and analyzed using the **ping** command.

| Website | IP Address | IP Class |
|----------|------------|----------|
| Apple.com | 17.253.144.10 | A |
| Twitter.com | 104.244.42.193 | A |
| Google.com | 142.250.200.142 | B |
| YouTube.com | 142.250.200.78 | B |
| Facebook.com | 102.132.101.35 | A |
| Wikipedia.org | 185.15.58.224 | B |
| Harvard.edu | 192.0.66.20 | C |
| ResearchGate.net | 104.18.41.9 | A |
| Academia.edu | 108.157.78.122 | A |

---

## 📷 Screenshot

> Add your Ping command screenshots here.

```
screenshots/ping-websites.png
```

---

# Exercise 2 – IP Address Classification

IP addresses were classified according to the first octet.

| Class | First Octet Range | Default Mask |
|--------|------------------|--------------|
| A | 0 – 127 | 255.0.0.0 |
| B | 128 – 191 | 255.255.0.0 |
| C | 192 – 223 | 255.255.255.0 |

---

# Exercise 3 – Reserved IP Address Ranges

Private IP addresses are reserved for internal network communication.

| Class | Private Range |
|--------|---------------|
| A | 10.0.0.0/8 |
| B | 172.16.0.0 – 172.31.255.255 |
| C | 192.168.0.0/16 |

### Observation

None of the analyzed public website IP addresses belong to these reserved ranges.

---

## Importance of Reserved IP Addresses

Reserved IP addresses are essential because they:

- Enable internal communication.
- Reduce IPv4 address exhaustion.
- Improve network security.
- Prevent routing conflicts.
- Support network segmentation.

---

# Exercise 4 – Device Capacity by IP Class

The maximum number of usable hosts depends on the number of host bits.

| Class | Formula | Usable Hosts |
|--------|----------|--------------|
| A | 2²⁴ − 2 | 16,777,214 |
| B | 2¹⁶ − 2 | 65,534 |
| C | 2⁸ − 2 | 254 |

---

# Exercise 5 – Subnetting

Example:

Starting Network

```
192.168.0.0/24
```

Subnetting into **/24**

```
Subnet Mask:
255.255.255.0

Usable Hosts

254
```

---

### /26 Example

| Subnet | Hosts |
|---------|-------|
| /26 | 62 usable hosts |

---

### /28 Example

| Subnet | Hosts |
|---------|-------|
| /28 | 14 usable hosts |

Smaller subnet masks increase the number of available hosts, while larger subnet masks create more subnets with fewer hosts.

---

# Exercise 6 – Default Subnet Masks

| Class | Default Mask |
|--------|--------------|
| A | 255.0.0.0 |
| B | 255.255.0.0 |
| C | 255.255.255.0 |

---

## Custom Subnetting

### /25

- Total Addresses: 128
- Usable Hosts: 126
- Number of Networks: 2

---

### /27

- Total Addresses: 32
- Usable Hosts: 30
- Number of Networks: 8

---

# Exercise 7 – Traceroute and GeoIP Analysis

The network path was analyzed using **Traceroute**, while IP ownership and location were verified using **IPinfo.io**.

## Apple IP Information

| Field | Value |
|--------|--------|
| IP Address | 17.253.144.10 |
| Hostname | advertising.apple.com |
| Company | Apple Inc. |
| ASN | AS714 |
| Country | United States |
| State | California |
| City | Cupertino |
| Time Zone | America/Los_Angeles |

---

### Abuse Contact

- Apple Abuse Team
- abuse@apple.com

---

## Screenshot

> Add your Traceroute screenshot.

```
screenshots/traceroute.png
```

---

# Latency vs Geographic Distance

Generally,

- Shorter distances produce lower latency.
- Longer distances increase round-trip time (RTT).

However, latency is also affected by:

- Network congestion
- ISP routing
- Number of hops
- Transmission media
- Server performance

---

# Key Learning Outcomes

During this lab, I learned how to:

- Identify public IP addresses.
- Classify IP address classes.
- Understand private IP ranges.
- Calculate usable hosts.
- Perform subnetting.
- Analyze network routes.
- Identify IP ownership using GeoIP tools.
- Relate latency to geographic distance.

---

# Skills Demonstrated

- IP Address Analysis
- Networking Fundamentals
- Subnetting
- Routing Concepts
- Network Diagnostics
- Traceroute
- GeoIP Analysis
- Linux Networking

---

# Screenshots

```
screenshots/
│
├── ping-websites.png
├── traceroute.png
├── geoip-result.png
└── subnet-calculation.png
```

---

# Conclusion

This lab provided practical experience in IP addressing, subnetting, routing, and network diagnostics. It strengthened my understanding of how IP addresses are assigned, how subnetting improves network organization, and how diagnostic tools such as **Ping**, **Traceroute**, and **GeoIP** can be used to analyze network connectivity and performance.
**Student:** Ayilara Busari Dare 
