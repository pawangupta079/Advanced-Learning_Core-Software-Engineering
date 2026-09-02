# Networking Fundamentals for DevOps

# Introduction

Networking is one of the most important foundations of DevOps, Cloud Computing, Kubernetes, Docker, and System Design.

Before learning Docker, Kubernetes, Azure, or Terraform, you must understand how computers communicate over a network.

By the end of this section, you should be able to answer:

- How does a browser open a website?
- How does a computer identify another computer?
- How does DNS work?
- What happens when you type google.com?
- How does HTTPS secure communication?
- How do cloud networks work?

---

# 1. What is Networking?

Networking is the process of connecting two or more devices so they can communicate and exchange data.

Examples:

- Laptop communicating with a router
- Mobile phone communicating with a server
- Browser communicating with a website
- Microservices communicating inside Kubernetes

Simple Example:

```text
Laptop
   |
   |
Router
   |
   |
Internet
   |
   |
Google Server
```

When you visit:

```text
https://www.google.com
```

your computer sends a request to Google's servers and receives a response.

---

# Key Networking Components

## Client

The device requesting information.

Examples:

- Browser
- Mobile App
- API Client

---

## Server

The device providing information.

Examples:

- Web Server
- Database Server
- Mail Server

---

## Router

A device that forwards network packets between different networks.

Example:

```text
Home Network
      |
   Router
      |
   Internet
```

---

## Switch

Connects devices inside the same local network.

Example:

```text
Computer A
Computer B
Computer C
      |
    Switch
```

---

## IP Address

Every device on a network needs an address.

Example:

```text
192.168.1.10
```

Like a house address.

Without an IP address, devices cannot communicate.

---

# Data Communication Process

Imagine opening:

```text
https://www.microsoft.com
```

Steps:

1. Browser requests website
2. DNS finds server IP
3. TCP connection established
4. HTTPS encryption starts
5. Request sent
6. Server responds
7. Browser displays page

---

# Types of Networks

## LAN (Local Area Network)

Small network.

Examples:

- Office network
- Home WiFi

```text
PC
 |
Switch
 |
PC
```

---

## WAN (Wide Area Network)

Large network connecting multiple locations.

Example:

```text
Delhi Office
      |
Internet
      |
Noida Office
```

---

## Internet

A global network connecting millions of devices.

---

# Network Devices

## Hub

Old device that sends data to every connected device.

Not commonly used today.

---

## Switch

Sends data only to the intended destination.

More efficient than a hub.

---

## Router

Connects multiple networks.

Example:

```text
Office Network
      |
   Router
      |
Internet
```

---

## Firewall

Filters network traffic.

Rules:

```text
Allow HTTP
Allow HTTPS
Block everything else
```

---

# Important Terminologies

## Packet

Data travels through networks in small units called packets.

Example:

```text
Large File
    |
Split
    |
Multiple Packets
```

---

## Port

A logical communication endpoint.

Example:

```text
IP Address + Port
```

Common ports:

| Service | Port |
|----------|--------|
| HTTP | 80 |
| HTTPS | 443 |
| SSH | 22 |
| FTP | 21 |
| DNS | 53 |

Example:

```text
192.168.1.10:80
```

---

## Protocol

A set of communication rules.

Examples:

- HTTP
- HTTPS
- TCP
- UDP
- DNS
- SSH

---

# Real-World Example

You open:

```text
https://github.com
```

Network flow:

```text
Browser
   |
DNS Lookup
   |
IP Address
   |
TCP Connection
   |
TLS Handshake
   |
HTTPS Request
   |
GitHub Server
   |
Response
```

---

# Why Networking Matters in DevOps

Every DevOps tool relies on networking.

Examples:

Docker:

```text
Container
      |
Container Network
      |
Another Container
```

Kubernetes:

```text
Pod
   |
Service
   |
Ingress
```

Azure:

```text
VM
|
Virtual Network
|
Internet
```

Terraform:

```text
Creates Networks
Creates Subnets
Configures Routes
```

Without networking knowledge:

- Docker becomes difficult
- Kubernetes becomes confusing
- Cloud networking becomes impossible

---

# Skills You Must Learn Next

1. OSI Model
2. TCP/IP Model
3. HTTP & HTTPS
4. DNS
5. DHCP
6. NAT
7. Load Balancer
8. Reverse Proxy
9. SSL/TLS
10. CIDR
11. Subnetting

---

# Mastery Goal

After completing Networking Fundamentals, you should be able to:

✅ Explain how the internet works

✅ Identify IP addresses and ports

✅ Understand client-server communication

✅ Troubleshoot connectivity problems

✅ Understand how cloud networking works

✅ Understand Kubernetes and Docker networking concepts

✅ Move confidently into advanced DevOps topics

---

