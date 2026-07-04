# Interfaces and Cables

## Ethernet

**Ethernet** is the most widely used LAN (Local Area Network) technology. It is a collection of **networking standards and protocols** that define how devices communicate over a wired network.

### Why do we need network protocols/standards?

Imagine two people trying to communicate:

- Person A speaks **English**
- Person B speaks **Japanese**

Without a common language, communication is impossible.

Networking works the same way. Devices from different manufacturers (Cisco, Dell, HP, Lenovo, etc.) need a common set of rules so they can communicate correctly.

These rules are called **network protocols** or **standards**.

Examples:

- **Physical standards**: Cable type, connector, voltage levels, pin layout
- **Logical standards**: IP addressing, MAC addressing, frame format

---

# Bits and Bytes

- **Bit (b)**: Smallest unit of data.
  - Possible values: `0` or `1`
- **Byte (B)**: Group of **8 bits**.

```
1 Byte = 8 Bits
```

Example:

```
01000001 = 1 Byte
```

---

## Network Speed

Network speed is measured in **bits per second (bps)**.

Examples:

- Kbps (Kilobits per second)
- Mbps (Megabits per second)
- Gbps (Gigabits per second)
- Tbps (Terabits per second)

> **Note:** Networking equipment (routers, switches, ISPs) always advertise speeds in **bits per second**, not bytes.

---

## File Transfer Speed

Operating systems usually display download speeds in **Bytes per second**.

Examples:

- KB/s
- MB/s
- GB/s

Since:

```
1 Byte = 8 Bits
```

Conversion:

```
1 MB/s = 8 Mbps

1 GB/s = 8 Gbps
```

Example:

If your internet speed is **100 Mbps**:

```
100 ÷ 8 = 12.5 MB/s
```

Maximum download speed will be approximately **12.5 MB/s**.

---

## Data Units

| Unit | Value |
|------|------:|
| 1 Kilobit (Kb) | 1,000 bits |
| 1 Megabit (Mb) | 1,000 Kb = 1,000,000 bits |
| 1 Gigabit (Gb) | 1,000 Mb = 1,000,000,000 bits |
| 1 Terabit (Tb) | 1,000 Gb = 1,000,000,000,000 bits |

---

# Ethernet Standards (Copper)

| Speed | Common Name | IEEE Standard | Ethernet Standard | Maximum Cable Length |
|-------:|-------------|---------------|-------------------|---------------------:|
| 10 Mbps | Ethernet | IEEE 802.3i | 10BASE-T | 100 m |
| 100 Mbps | Fast Ethernet | IEEE 802.3u | 100BASE-T | 100 m |
| 1 Gbps | Gigabit Ethernet | IEEE 802.3ab | 1000BASE-T | 100 m |
| 10 Gbps | 10 Gigabit Ethernet | IEEE 802.3an | 10GBASE-T | 100 m |

---

## Understanding Ethernet Naming

Example:

### 1000BASE-T

- **1000** → Speed (1000 Mbps = 1 Gbps)
- **BASE** → Baseband signaling
- **T** → Twisted Pair cable

Example:

```
10BASE-T

10      → 10 Mbps
BASE    → Baseband
T       → Twisted Pair
```

---

# Physical Cables

The most commonly used copper cable in Ethernet networks is the **UTP cable**.

```
UTP = Unshielded Twisted Pair
```

---

## Why are the wires twisted?

The wires are twisted to reduce:

- Electromagnetic Interference (EMI)
- Crosstalk (interference between cable pairs)

Twisting ensures that external electrical noise affects both wires equally, allowing the receiver to cancel the interference.

This improves signal quality and data reliability.

---

## Electromagnetic Interference (EMI)

**EMI** is unwanted electrical noise that can interfere with data transmission.

Common sources include:

- Power cables
- Electric motors
- Transformers
- Fluorescent lights
- Microwave ovens

Excessive EMI can cause:

- Data corruption
- Packet loss
- Reduced network performance

---

## UTP Cable Structure

A standard Ethernet UTP cable contains:

- **4 Twisted Pairs**
- **8 Copper Wires**

```
4 Pairs = 8 Wires
```

### Wire Colors

```
White/Orange
Orange

White/Green
Green

White/Blue
Blue

White/Brown
Brown
```

---

## Ethernet Speeds and Wire Usage

| Speed | Cable Pairs Used |
|-------:|------------------|
| 10 Mbps | 2 Pairs (4 Wires) |
| 100 Mbps | 2 Pairs (4 Wires) |
| 1 Gbps | 4 Pairs (8 Wires) |
| 10 Gbps | 4 Pairs (8 Wires) |

---

# Key Points (CCNA)

- Ethernet is the most common wired LAN technology.
- Ethernet standards are defined by the **IEEE 802.3** family.
- Network speed is measured in **bits per second (bps)**.
- File transfers are usually shown in **Bytes per second (B/s)**.
- `1 Byte = 8 Bits`.
- UTP stands for **Unshielded Twisted Pair**.
- Twisted wires reduce **EMI** and **crosstalk**.
- Maximum length for standard Ethernet copper cables is **100 meters**.
- Gigabit Ethernet and above use **all four twisted pairs**.
