# Ethernet LAN Switching

## Protocol Data Units (PDUs)

As data moves down the TCP/IP stack, each layer adds its own header (and sometimes a trailer). The resulting unit of data at each layer is called a **Protocol Data Unit (PDU)**.

| Layer | PDU | Description |
|-------|-----|-------------|
| Application | Data | Original user data |
| Transport | Segment (TCP) / Datagram (UDP) | Transport header is added |
| Internet | Packet | IP header is added |
| Data Link | Frame | Ethernet header and trailer are added |
| Physical | Bits | Frame is converted into electrical, optical, or radio signals |

### Encapsulation Process

```
Application
    Data
      │
      ▼
Transport
[TCP/UDP Header | Data]
      │
      ▼
Internet
[IP Header | TCP/UDP Header | Data]
      │
      ▼
Data Link
[Ethernet Header | Packet | Ethernet Trailer]
      │
      ▼
Physical
Bits (0s and 1s)
```

> **Encapsulation** is the process of adding headers (and trailers) as data moves down the network stack.

---

# Ethernet Frame

An Ethernet Frame is the PDU of the **Data Link Layer (Layer 2)**.

It encapsulates an IP packet before it is transmitted over the network.

```
+----------+-----+-----------+--------+----------+---------+-----+
|Preamble  | SFD | Destination| Source | Type/Len |  Data   | FCS |
+----------+-----+-----------+--------+----------+---------+-----+
```

---

## Ethernet Frame Fields

| Field | Size | Purpose |
|--------|-----:|---------|
| Preamble | 7 Bytes | Synchronizes sender and receiver |
| SFD | 1 Byte | Marks the start of the frame |
| Destination MAC | 6 Bytes | MAC address of the receiving device |
| Source MAC | 6 Bytes | MAC address of the sending device |
| Type/Length | 2 Bytes | Indicates the encapsulated protocol or payload length |
| Data | 46–1500 Bytes | Encapsulated Layer 3 packet |
| FCS | 4 Bytes | Error detection using CRC |

**Ethernet Header:** 14 Bytes

**Ethernet Trailer:** 4 Bytes

**Preamble + SFD:** 8 Bytes

**Total Ethernet Overhead:** **26 Bytes**

---

# Preamble

**Size:** 7 Bytes (56 bits)

### Purpose

The Preamble synchronizes the sender's and receiver's clocks before data transmission begins.

### Pattern

```
10101010 repeated 7 times
```

Without synchronization, the receiver may not correctly interpret incoming bits.

---

# Start Frame Delimiter (SFD)

**Size:** 1 Byte

### Purpose

Marks the **end of the Preamble** and indicates the **start of the Ethernet Frame**.

### Binary Value

```
10101011
```

---

# Destination MAC Address

**Size:** 6 Bytes (48 bits)

Specifies the MAC address of the device that should receive the frame.

Example:

```
00:1A:2B:3C:4D:5E
```

The switch examines this field to determine where to forward the frame.

---

# Source MAC Address

**Size:** 6 Bytes (48 bits)

Contains the MAC address of the sender.

Switches learn MAC addresses by reading the **Source MAC** field and storing it in the MAC Address Table (CAM Table).

---

# Type / Length Field

**Size:** 2 Bytes (16 bits)

This field has two possible meanings:

### 1. Length

If the value is **1500 or less**, it indicates the length of the payload.

### 2. EtherType

If the value is **1536 or greater (0x0600)**, it identifies the Layer 3 protocol encapsulated inside the frame.

### Common EtherTypes

| Protocol | EtherType (Hex) | Decimal |
|-----------|-----------------|---------|
| IPv4 | 0x0800 | 2048 |
| ARP | 0x0806 | 2054 |
| IPv6 | 0x86DD | 34525 |

---

# Data Field

Contains the Layer 3 packet (usually an IPv4 or IPv6 packet).

### Minimum Size

46 Bytes

### Maximum Size

1500 Bytes

If the payload is smaller than 46 bytes, padding is added to meet the minimum Ethernet frame size.

---

# Frame Check Sequence (FCS)

**Size:** 4 Bytes (32 bits)

The FCS is used for **error detection**.

The sender calculates a CRC (Cyclic Redundancy Check) value and stores it in the FCS field.

The receiver performs the same calculation.

- If both values match → Frame is accepted.
- If they differ → Frame is discarded.

> **Important:** FCS only detects errors. It does **not** correct them.

---

# Cyclic Redundancy Check (CRC)

CRC is an error-detection algorithm used by Ethernet.

### Process

1. Sender calculates CRC.
2. CRC is stored in the FCS field.
3. Receiver calculates CRC again.
4. Values are compared.
5. If different, the frame is dropped.

---

# MAC Address

A **MAC (Media Access Control) Address** is a unique physical address assigned to a Network Interface Card (NIC).

### Properties

- Size: **48 bits (6 Bytes)**
- Assigned by the manufacturer
- Usually permanent (Burned-In Address or BIA)
- Used at the **Data Link Layer (Layer 2)**

Example:

```
00:1A:2B:3C:4D:5E
```

---

## MAC Address Structure

A MAC address consists of **6 bytes**.

```
00:1A:2B : 3C:4D:5E
|-------| |--------|
   OUI      Device ID
```

### Organizationally Unique Identifier (OUI)

- First **24 bits (3 Bytes)**
- Identifies the manufacturer
- Assigned by IEEE

Examples:

- Cisco
- Intel
- Dell
- HP

---

### Device Identifier

- Last **24 bits (3 Bytes)**
- Assigned by the manufacturer
- Makes each device unique

---

## MAC Address Format

MAC addresses are represented using **12 hexadecimal digits**.

Common formats:

```
00:1A:2B:3C:4D:5E

00-1A-2B-3C-4D-5E

001A.2B3C.4D5E
```

---

# Important CCNA Points

- Data Link Layer PDU = **Frame**
- Network Layer PDU = **Packet**
- Transport Layer PDU = **Segment (TCP)** / **Datagram (UDP)**
- Physical Layer transmits **Bits**
- Ethernet Header = **14 Bytes**
- Ethernet Trailer = **4 Bytes**
- Ethernet Overhead = **26 Bytes**
- MAC Address = **48 bits (6 Bytes)**
- Destination MAC = Receiver's MAC Address
- Source MAC = Sender's MAC Address
- IPv4 EtherType = **0x0800**
- ARP EtherType = **0x0806**
- IPv6 EtherType = **0x86DD**
- FCS uses **CRC** for error detection.
- Switches learn devices using the **Source MAC Address**, not the Destination MAC Address.
