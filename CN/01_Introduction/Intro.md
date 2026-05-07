
# Introduction to Computer Networks

Computer Networks is one of the most important subjects for placements, interviews, and real-world software engineering.

Almost every modern application depends on networks:
- Websites
- Mobile apps
- Cloud systems
- Online games
- Video calls
- Banking systems

Understanding how computers communicate helps you become a better developer and engineer.

---

# What is a Computer Network?

A computer network is a group of computers and devices connected together to share data and resources.

These devices communicate using communication protocols.

Examples of devices in a network:
- Computers
- Mobile phones
- Servers
- Routers
- Printers

Examples of resources shared:
- Files
- Internet connection
- Printers
- Storage

---

# Why Do We Need Computer Networks?

Networks help in:
- Fast communication
- File sharing
- Internet access
- Remote work
- Cloud computing
- Online services

Without networks:
- The internet would not exist
- Email would not work
- Websites could not communicate with users

---

# Types of Networks

Networks are divided based on geographical area.

---

# 1. LAN (Local Area Network)

A LAN connects devices within a small area.

Examples:
- Home WiFi
- School computer lab
- Office network

Features:
- High speed
- Small coverage area
- Low cost
- Easy maintenance

Example:
If all computers in a college lab are connected together, it forms a LAN.

---

# 2. MAN (Metropolitan Area Network)

A MAN covers a larger area than a LAN, usually a city or large campus.

Examples:
- City-wide cable network
- University network across campuses

Features:
- Covers a city-sized area
- Faster than WAN
- More expensive than LAN

---

# 3. WAN (Wide Area Network)

A WAN covers a very large geographical area such as countries or continents.

Example:
- The Internet

Features:
- Large coverage area
- Uses public communication systems
- Slower compared to LAN
- Expensive infrastructure

Real-world example:
When you access a website hosted in another country, WAN communication is happening.

---

# Comparison of LAN, MAN, and WAN

| Feature       | LAN         | MAN          | WAN        |
|---------------|-------------|--------------|------------|
| Coverage Area | Small       | Medium       | Very Large |
| Speed         | Fast        | Moderate     | Slower     |
| Cost          | Low         | Medium       | High       |
| Example       | Office WiFi | City Network | Internet   |

---

# Network Topology

Topology means the arrangement of devices in a network.

It describes how computers are connected to each other.

---

# Types of Network Topology

## 1. Bus Topology

All devices are connected to a single cable called the bus.

### Advantages
- Simple
- Low cost

### Disadvantages
- If the main cable fails, the network stops
- Performance decreases with more devices

---

# 2. Star Topology

All devices are connected to a central device such as a switch or hub.

### Advantages
- Easy to manage
- Failure of one device does not affect others

### Disadvantages
- If the central device fails, the network fails

This is the most commonly used topology today.

---

# 3. Ring Topology

Devices are connected in a circular form.

Data travels in one direction.

### Advantages
- Organized communication

### Disadvantages
- Failure of one device can affect the network

---

# 4. Mesh Topology

Every device is connected to every other device.

### Advantages
- Highly reliable
- Multiple paths available

### Disadvantages
- Expensive
- Complex wiring

Used in:
- Military systems
- Critical communication systems

---

# 5. Tree Topology

Combination of star and bus topology.

Used in:
- Large organizations

---

# Client-Server vs Peer-to-Peer (P2P)

These are two major network architectures.

---

# Client-Server Architecture

In this model:
- A central server provides services
- Clients request services

Example:
- Web browsing
- Banking apps
- Gmail

### How It Works
1. Client sends request
2. Server processes request
3. Server sends response

### Advantages
- Centralized management
- Better security
- Easy backup

### Disadvantages
- Server failure affects all clients
- Expensive setup

---

# Peer-to-Peer (P2P) Architecture

In P2P:
- No central server exists
- All devices can act as both client and server

Example:
- Torrent systems
- Local file sharing

### Advantages
- Low cost
- No dependency on a central server

### Disadvantages
- Lower security
- Hard to manage
- Data backup is difficult

---

# Client-Server vs P2P Comparison

| Feature        | Client-Server | P2P       |
|----------------|---------------|-----------|
| Central Server | Yes           | No        |
| Security       | High          | Lower     |
| Cost           | Higher        | Lower     |
| Management     | Easy          | Difficult |
| Example        | Gmail         | Torrent   |

---

# Bandwidth vs Throughput

These two terms are very commonly asked in interviews.

---

# What is Bandwidth?

Bandwidth is the maximum amount of data that can be transferred over a network in a given time.

It represents the capacity of the network.

Unit:
- bits per second (bps)

Example:
If an internet connection supports 100 Mbps, then its bandwidth is 100 Mbps.

---

# What is Throughput?

Throughput is the actual amount of data successfully transferred over the network.

Throughput is usually lower than bandwidth because of:
- Network congestion
- Delay
- Errors
- Hardware limitations

Example:
Bandwidth = 100 Mbps

Actual speed received = 70 Mbps

Then:
- Bandwidth = 100 Mbps
- Throughput = 70 Mbps

---

# Bandwidth vs Throughput Comparison

| Feature                  | Bandwidth        | Throughput              |
|--------------------------|------------------|-------------------------|
| Meaning                  | Maximum capacity | Actual data transferred |
| Theoretical or Practical | Theoretical      | Practical               |
| Value                    | Usually higher   | Usually lower           |

---

# What is Latency?

Latency is the time taken for data to travel from source to destination.

It is also called network delay.

Unit:
- milliseconds (ms)

Lower latency means faster communication.

---

# Causes of Latency

- Long physical distance
- Network congestion
- Slow hardware
- Too many routers/switches

---

# Examples of Latency

## Low Latency
- Online gaming
- Video calls

These require very fast communication.

---

## High Latency
- Satellite communication

Data travels a very large distance, causing delay.

---

# Important Interview Questions

1. What is a computer network?
2. Difference between LAN, MAN, and WAN
3. Explain network topology
4. Difference between bandwidth and throughput
5. What is latency?
6. Difference between client-server and P2P
7. Which topology is most commonly used?
8. Why is throughput usually lower than bandwidth?

---

# Quick Revision Notes

- LAN = Small area network
- MAN = City-level network
- WAN = Large/global network
- Internet is a WAN
- Topology = Arrangement of devices
- Star topology is most common
- Client-server uses a central server
- P2P has no central server
- Bandwidth = Maximum capacity
- Throughput = Actual speed
- Latency = Delay in communication

```
````
