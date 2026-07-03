---
title: Networking Devices - Part 1
description: CCNA Deep Notes - Introduction, NIC, Repeater, and Hub
tags:
  - CCNA
  - Networking
  - Cisco
  - Networking Fundamentals
  - Devices
---

# Networking Devices (Part 1)

> [!NOTE]
> These notes are written assuming **zero networking knowledge**. By the end of this chapter, you should understand **why networking devices exist**, **what problem they solve**, and **how they work internally**.

---

# Table of Contents

- Introduction to Networking Devices
- Why Do We Need Networking Devices?
- How Communication Happens in a Network
- Types of Networking Devices
- Network Interface Card (NIC)
- Repeater
- Hub
- Device Comparison
- CCNA Exam Tips
- Practice Questions

---

# Introduction to Networking Devices

Imagine you are living in a city.

There are:

- Houses
- Roads
- Traffic lights
- Highways
- Security checkpoints
- Toll booths
- Postal offices

Without these things, moving from one place to another would be chaotic.

Computer networks work exactly the same way.

Instead of people moving through roads,

**data** moves through **network devices**.

Networking devices act like traffic managers that ensure data reaches the correct destination quickly, efficiently, and securely.

Without networking devices:

- Computers would not know where to send data.
- Devices would interfere with each other.
- Networks could not grow beyond a few computers.
- The Internet would not exist.

Networking devices are the backbone of every network.

---

# What is a Computer Network?

A computer network is a collection of devices connected together so they can exchange information.

Examples of devices include:

- Computers
- Laptops
- Smartphones
- Servers
- Printers
- Cameras
- IoT devices

These devices are called **End Devices** because they generate or consume data.

Example:

```
Laptop -------- Laptop
     \            /
      \          /
      Printer   Phone
```

This small group of connected devices forms a network.

---

# Why Can't Computers Connect Directly?

Suppose you have two computers.

```
PC A -------- PC B
```

Easy.

Now imagine 100 computers.

Should every computer have a cable to every other computer?

```
PC1 ----- PC2
 | \      / |
 |  \    /  |
 |   \  /   |
 |    \/    |
Many More Connections...
```

This quickly becomes impossible.

Problems include:

- Thousands of cables
- High cost
- Difficult maintenance
- Poor scalability
- Difficult troubleshooting

Networking devices solve this problem by acting as central communication points.

Instead of connecting every computer to every other computer, each computer connects to a central device.

```
          Switch
        /   |   \
      PC1  PC2  PC3
```

This is much simpler, cheaper, and scalable.

---

# How Does Data Travel?

When one computer wants to send data to another, it doesn't magically appear at the destination.

The data follows several steps.

Suppose:

PC A wants to send a photo to PC B.

```
PC A
  |
  |
Network Device
  |
  |
PC B
```

The process is:

1. PC A creates the data.
2. The operating system prepares the data.
3. The data is converted into network frames.
4. The frame is sent through the NIC.
5. The networking device receives it.
6. The networking device decides where to send it.
7. The destination receives the frame.
8. The destination reconstructs the original data.

Notice something important.

The networking device **does not create the data.**

It simply helps move it.

Think of it like a courier company.

The courier doesn't write your letter.

It simply delivers it.

---

# Types of Networking Devices

The most common networking devices are:

| Device | Main Purpose |
|----------|-------------|
| NIC | Connects a device to a network |
| Repeater | Strengthens weak signals |
| Hub | Connects multiple devices (broadcasts data) |
| Bridge | Connects LAN segments |
| Switch | Intelligently forwards frames |
| Router | Connects different networks |
| Wireless Access Point | Provides Wi-Fi |
| Modem | Connects to ISP |
| Firewall | Filters traffic |
| Gateway | Connects different protocols or networks |

In this chapter we'll cover the first three.

---

# Network Interface Card (NIC)

---

# What is a NIC?

NIC stands for

**Network Interface Card**

It is the hardware component that allows a computer to communicate over a network.

Without a NIC,

your computer has no way of sending or receiving network data.

Think of it as the **mouth and ears** of the computer.

Without them,

communication is impossible.

---

# Real-World Analogy

Imagine you own a house.

The postal service can only deliver letters if your house has:

- an address
- a mailbox

No mailbox?

No delivery.

A NIC works similarly.

It gives your computer:

- a way to connect
- a unique identity (MAC Address)
- a method to send and receive data

---

# Where is the NIC Located?

Desktop

Usually installed on the motherboard or as a PCIe expansion card.

Laptop

Integrated into the motherboard.

Smartphone

Integrated into the chipset.

Server

May have multiple NICs.

Example:

```
Server

+-----------------------+

NIC 1  → Office Network

NIC 2  → Backup Network

NIC 3  → Internet

+-----------------------+
```

Servers often use multiple NICs for redundancy and higher bandwidth.

---

# Types of NIC

## Wired NIC

Uses Ethernet cables.

```
Computer
    |
Ethernet Cable
    |
Switch
```

Advantages

- Faster
- Lower latency
- More reliable

---

## Wireless NIC

Uses radio waves.

```
Laptop )))))

        Wi-Fi

Access Point
```

Advantages

- Mobility
- No cables

Disadvantages

- More interference
- Slightly slower than Ethernet

---

# Main Functions of a NIC

A NIC performs several important tasks.

## 1. Provides Physical Connectivity

It connects the computer to the network.

Without this connection,

communication cannot happen.

---

## 2. Stores the MAC Address

Every NIC has a unique identifier called the

**MAC Address**

Example

```
00:1A:2B:3C:4D:5E
```

Think of it as the hardware serial number of the network interface.

No two legitimate NICs should have the same MAC address.

---

## 3. Converts Data into Signals

The computer understands binary data.

The network cable carries electrical signals.

The NIC converts between these forms.

```
Binary Data

↓

Electrical Signals

↓

Cable
```

For wireless NICs:

```
Binary

↓

Radio Waves

↓

Air
```

---

## 4. Receives Incoming Data

Incoming electrical signals arrive.

The NIC converts them back into binary.

The operating system then processes them.

---

# Internal Working of a NIC

Suppose you open YouTube.

```
Browser

↓

Operating System

↓

TCP/IP Stack

↓

NIC

↓

Ethernet Cable
```

The NIC performs tasks such as:

- adding source MAC
- adding destination MAC
- calculating error detection values
- transmitting bits

On the receiving computer,

the NIC performs the reverse process.

---

# OSI Layer

The NIC mainly works at:

Layer 2 (Data Link)

It also interacts with Layer 1 because it sends electrical or radio signals.

---

# Key Points

✔ Every network-enabled device has at least one NIC.

✔ Every NIC has a MAC Address.

✔ NICs send and receive frames.

---

# Repeater

---

# Why Do We Need a Repeater?

Electrical signals become weaker over distance.

This phenomenon is called **signal attenuation**.

Imagine shouting across a football field.

The farther your voice travels,

the weaker it becomes.

Network signals behave the same way.

---

# Problem

Ethernet cables have a maximum recommended length of approximately **100 meters**.

Beyond that,

signals become unreliable.

---

# Solution

A repeater regenerates weak signals.

It does NOT understand the data.

It simply restores the signal strength.

---

# Real-World Analogy

Imagine someone relaying a message:

You:

"HELLO!"

Person in the middle:

"HELLO!"

Friend hears clearly.

The middle person isn't interpreting the message.

They're simply repeating it.

A repeater behaves similarly.

---

# Internal Working

```
Weak Signal

↓

Repeater Receives

↓

Amplifies

↓

Regenerates

↓

Strong Signal

↓

Destination
```

Notice:

It does **not** inspect:

- IP Address
- MAC Address
- Frame
- Packet

It only regenerates electrical or optical signals.

---

# OSI Layer

Layer 1

Physical Layer

Because it works only with bits and signals.

---

# Advantages

- Extends cable distance
- Reduces signal loss
- Simple
- Inexpensive

---

# Disadvantages

- Doesn't reduce traffic
- Doesn't improve security
- Doesn't filter data
- Still forwards noise if present

---

# Hub

---

# What is a Hub?

A Hub is essentially

> A **multi-port repeater.**

Instead of regenerating signals between two devices,

it regenerates signals for many devices.

---

# Why Was the Hub Invented?

Imagine a classroom.

Ten students need to communicate.

Instead of connecting every student to every other student,

everyone talks through one central person.

That's the Hub.

---

# Internal Working

Suppose:

PC1 sends data to PC3.

```
      Hub

PC1 PC2 PC3 Printer
```

The Hub receives the bits.

Because it has **no intelligence**,

it simply copies the incoming bits to every other port.

```
Incoming Frame

↓

Hub

↓

Port 1

Port 2

Port 3

Port 4

Port 5
```

Every connected device receives the frame.

Only the destination processes it.

Everyone else discards it.

---

# Why is this Inefficient?

Imagine a teacher making every announcement to every student,

even if only one student needs the information.

This wastes time.

Similarly,

a Hub creates unnecessary network traffic.

---

# Collision Domain

A collision happens when two devices transmit at the same time.

Example

```
PC1 -----

           Hub

PC2 -----
```

If both send simultaneously,

their signals collide.

Neither transmission succeeds.

Both must retransmit.

---

# Why Were Collisions Common?

Because Hubs use

**Half Duplex Communication**

This means:

A device can either:

- transmit

OR

- receive

Not both simultaneously.

Think of a walkie-talkie.

Only one person talks at a time.

---

# CSMA/CD

To reduce collisions,

devices connected to Hubs use

**Carrier Sense Multiple Access with Collision Detection (CSMA/CD)**

The process:

1. Listen to the cable.
2. If busy, wait.
3. If free, transmit.
4. Detect collision.
5. Stop transmitting.
6. Wait a random amount of time.
7. Try again.

This works,

but becomes inefficient as more devices join.

---

# Broadcast Behavior

The Hub sends every frame to every port.

Example:

```
PC1 → Hub

↓

Hub sends to

PC2

PC3

PC4

Printer

Server
```

Only one device needs the data,

but everyone receives it.

---

# Security Problems

Since everyone receives every frame,

an attacker can easily capture traffic.

This makes Hubs very insecure.

---

# Why Hubs Are Obsolete

Modern networks use switches because they:

- reduce collisions
- improve security
- improve speed
- forward data intelligently

Today,

Hubs are almost never used in production networks.

---

# Comparison

| Feature | NIC | Repeater | Hub |
|----------|------|-----------|------|
| Primary Purpose | Connect a device | Regenerate signals | Connect multiple devices |
| OSI Layer | Layer 2 (uses Layer 1 for signaling) | Layer 1 | Layer 1 |
| Uses MAC Address | Yes | No | No |
| Intelligent | No | No | No |
| Filters Traffic | No | No | No |
| Broadcasts to All Ports | No | No | Yes |

---

# CCNA Exam Tips

> [!IMPORTANT]
>
> - A Hub is a **multi-port repeater**.
> - Repeaters and Hubs operate at **Layer 1**.
> - A NIC contains a **MAC Address**.
> - Hubs do **not** maintain a MAC Address Table.
> - Hubs do **not** inspect frames.
> - Hubs create **one collision domain**.
> - Hubs use **half-duplex** communication.
> - Devices connected to Hubs rely on **CSMA/CD** to handle collisions.

---

# Quick Revision

- **NIC**: Connects a device to the network, stores the MAC address, and converts data to network signals.
- **Repeater**: Regenerates weak signals without inspecting the data.
- **Hub**: A multi-port repeater that broadcasts incoming data to every connected device, leading to collisions and poor efficiency.

---

# Practice Questions

1. What is the primary function of a NIC?
2. Why does signal attenuation occur?
3. At which OSI layer does a repeater operate?
4. Why is a hub called a multi-port repeater?
5. What is the difference between a hub and a switch?
6. Why do hubs create collisions?
7. What is CSMA/CD, and why is it needed with hubs?
8. Why are hubs rarely used in modern networks?
9. Which networking device stores a MAC address?
10. Explain the journey of data from a browser to a NIC before it leaves the computer.

---
➡️ **Next Chapter (Part 2):** **Bridge and Switch (Deep Dive)** — We'll cover MAC learning, CAM tables, forwarding, flooding, collision domains, broadcast domains, switching methods, duplex modes, VLAN basics, and Cisco switch commands.
