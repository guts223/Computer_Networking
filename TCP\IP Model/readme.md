# TCP/IP Model

## Who Defines Networking Standards?

Different organizations develop networking standards and protocols to ensure devices from different manufacturers can communicate with each other.

### IEEE (Institute of Electrical and Electronics Engineers)

- Develops standards mainly for **Local Area Networks (LANs)**.
- Responsible for Ethernet and Wi-Fi standards.

**Examples:**

- Ethernet (IEEE 802.3)
- Wi-Fi (IEEE 802.11)

---

### IETF (Internet Engineering Task Force)

- An open international organization that develops protocols used on the Internet.
- Publishes standards through RFCs (Request for Comments).

**Examples:**

- TCP
- IP
- UDP
- HTTP
- HTTPS
- DNS
- SMTP

---

# TCP/IP Model

The TCP/IP model describes how data travels from one device to another over a network.

It consists of **5 layers**.

| Layer | Main Function | Example Protocols |
|--------|---------------|-------------------|
| Application | Provides network services to applications | HTTP, HTTPS, DNS, FTP, SMTP |
| Transport | End-to-end communication between applications | TCP, UDP |
| Internet | Logical addressing and routing | IPv4, IPv6, ICMP |
| Network Access (Local Network) | Communication within the local network | Ethernet, Wi-Fi, ARP |
| Physical | Transmits bits over the physical medium | UTP, Fiber, Radio Signals |

---
![[Pasted image 20260706061044.png]]
# Layer 1 - Physical Layer

The Physical Layer is responsible for transmitting **raw bits (0s and 1s)** over the physical medium.

It converts digital data into electrical, optical, or radio signals and vice versa.

## Responsibilities

- Sends and receives bits
- Defines cables and connectors
- Defines electrical and optical signaling
- Defines transmission speed
- Defines maximum cable length

---

## Examples

- UTP Cables
- Fiber Optic Cables
- Wi-Fi Radio Signals
- NIC Physical Interface

---

## Devices

- Hub
- Repeater
- Cables
- Connectors

---

# Layer 2 - Network Access (Local Network) Layer

The Network Access Layer is responsible for communication **within the same local network (LAN).**

It uses **MAC Addresses** to identify devices.

Communication at this layer is called **Hop-to-Hop Delivery**.

---

## What is a Hop?

A **hop** is the movement of data from one Layer 3 device (router) to another.

Example:

```
PC → Router → Router → Server

Total Hops = 2
```

> **Note:** Switches do **not** increase the hop count because they operate at Layer 2.

---

## Responsibilities

- Frame creation
- MAC Addressing
- Error detection (FCS)
- Local delivery
- Access to the physical medium

---

## Protocols

- Ethernet
- Wi-Fi
- ARP (Address Resolution Protocol)

---

## ARP (Address Resolution Protocol)

ARP maps an **IPv4 Address** to a **MAC Address**.

Example:

```
IP Address

192.168.1.10

↓

ARP

↓

MAC Address

00:1A:2B:3C:4D:5E
```

Before sending an Ethernet frame, a device must know the destination MAC address. ARP is used to discover it.

---

## Devices

- Switch
- Bridge

---

# Layer 3 - Internet Layer

The Internet Layer is responsible for delivering packets **between different networks**.

Unlike the Network Access Layer, communication is not limited to the local LAN.

It uses **IP Addresses** to identify devices.

---

## Responsibilities

- Logical addressing
- Routing
- Packet forwarding
- Path selection

---

## Devices

- Router
- Layer 3 Switch

---

## Protocols

- IPv4
- IPv6
- ICMP

---

## ICMP (Internet Control Message Protocol)

Used for:

- Error reporting
- Network diagnostics

Examples:

- `ping`
- `traceroute`

---

# Layer 4 - Transport Layer

The Transport Layer provides **end-to-end communication** between applications running on different devices.

It identifies applications using **Port Numbers**.

Example:

```
Computer

Chrome → Port 443

Discord → Port 50000+

SSH → Port 22
```

---

## Responsibilities

- Segmentation
- Reassembly
- Reliability
- Error recovery
- Flow control
- Port addressing

---

## Protocols

### TCP (Transmission Control Protocol)

Features:

- Reliable
- Connection-oriented
- Guarantees delivery
- Error checking
- Packet ordering

Used for:

- HTTP/HTTPS
- SSH
- FTP
- Email

---

### UDP (User Datagram Protocol)

Features:

- Fast
- Connectionless
- No guarantee of delivery
- No retransmission

Used for:

- VoIP
- Online Gaming
- Streaming
- DNS

---

# Layer 5 - Application Layer

The Application Layer is the interface between **network applications** and the network.

It defines how applications exchange data.

---

## Responsibilities

- Data formatting
- Application communication
- Authentication
- File transfer
- Email
- Web browsing

---

## Common Protocols

### Web

- HTTP
- HTTPS

### File Transfer

- FTP
- TFTP

### Email

- SMTP (Send Email)
- POP3 (Download Email)
- IMAP (Synchronize Email)

### Name Resolution

- DNS

---

# Protocol Summary

| Layer | Common Protocols |
|--------|------------------|
| Application | HTTP, HTTPS, FTP, TFTP, SMTP, POP3, IMAP, DNS |
| Transport | TCP, UDP |
| Internet | IPv4, IPv6, ICMP |
| Network Access | Ethernet, Wi-Fi, ARP |
| Physical | UTP, Fiber, Radio Signals |

---

# Quick Revision

- **IEEE** develops LAN standards like Ethernet and Wi-Fi.
- **IETF** develops Internet protocols like TCP, IP, HTTP, and DNS.
- **Physical Layer** transmits bits over cables or wireless media.
- **Network Access Layer** provides communication within the local network using MAC addresses.
- **ARP** maps IPv4 addresses to MAC addresses.
- **Internet Layer** routes packets using IP addresses.
- **Transport Layer** provides end-to-end communication using TCP or UDP.
- **Application Layer** provides network services to user applications.
- **Switches do not increase hop count; routers do.**
