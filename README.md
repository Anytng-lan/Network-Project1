# ✨ **Network Design for JK Network Solutions**

![Network](https://img.shields.io/badge/Network-Design-blue.svg) ![Routing](https://img.shields.io/badge/Dynamic-Routing-green.svg) ![OSPF](https://img.shields.io/badge/OSPF-Enabled-yellow.svg)

---

## 📑 **Table of Contents**

1. [Introduction](#introduction)
2. [Network Topology Design](#network-topology-design)
   - [Topology Selection](#topology-selection)
3. [IP Addressing Scheme](#ip-addressing-scheme)
   - [IP Address Allocation](#ip-address-allocation)
   - [Justification for IP Addressing](#justification-for-ip-addressing)
4. [Routing Strategy for Inter-Floor Communication](#routing-strategy-for-inter-floor-communication)
   - [Dynamic Routing Approach](#dynamic-routing-approach)
   - [Network Devices and Placement](#network-devices-and-placement)
   - [Default Gateways](#default-gateways)
5. [Network Diagram](#network-diagram)
6. [Conclusion](#conclusion)
7. [Recommendations](#recommendations)

---

## 📌 **1. Introduction**
JK Network Solutions is a mid-sized enterprise with a seven-floor office building. The network is designed to be **efficient, scalable, and fault-tolerant** while maintaining optimal cost-performance ratios. The solution incorporates **ring and mesh topologies, structured IP addressing, and dynamic OSPF routing** for inter-floor communication.

---

## 🔗 **2. Network Topology Design**
### 🏗 **2.1 Topology Selection**

#### 🏢 **Floors 1-3: Ring Topology** 🔄
Each computer connects to two others, forming a circular data path.

✅ **Advantages:**
- Fault Tolerance: Data reroutes if one connection fails.
- Predictable Performance: Reduces data collisions.

⚠ **Disadvantages:**
- Scalability issues when adding new devices.
- Single Point of Failure: The entire ring is affected if a device fails.

#### 🏢 **Floors 4-7: Mesh Topology** 🕸
Each computer connects to multiple others, providing redundant paths.

✅ **Advantages:**
- High Fault Tolerance: Multiple routes prevent downtime.
- Scalability: New devices integrate easily.

⚠ **Disadvantages:**
- Complexity: Requires more cabling and configuration.
- Cost: Higher implementation and maintenance expenses.

---

## 🌍 **3. IP Addressing Scheme**
### 📡 **3.1 IP Address Allocation**
The IP addressing ensures uniqueness and future scalability.

#### 🏢 **Floors 1-2: Class B Private IPv4 Addresses**
| Floor  | IP Range          | Subnet Mask   | Default Gateway | Router IP       |
|--------|------------------|--------------|----------------|----------------|
| Floor 1 | 172.16.0.2 - 172.16.0.9 | 255.255.0.0 | 172.16.0.1 | 172.18.0.1 |
| Floor 2 | 172.17.0.2 - 172.17.0.9 | 255.255.0.0 | 172.17.0.1 | 172.18.0.2 |

#### 🏢 **Floors 3-7: Class C Public IPv4 Addresses**
| Floor  | IP Range          | Subnet Mask   | Default Gateway |
|--------|------------------|--------------|----------------|
| Floor 3 | 196.0.0.2 - 196.0.0.9 | 255.255.255.0 | 196.0.0.1 |
| Floor 4 | 197.0.0.2 - 197.0.0.9 | 255.255.255.0 | 197.0.0.1 |
| Floor 5 | 198.0.0.2 - 198.0.0.9 | 255.255.255.0 | 198.0.0.1 |
| Floor 6 | 199.0.0.2 - 199.0.0.9 | 255.255.255.0 | 199.0.0.1 |
| Floor 7 | 200.0.0.2 - 200.0.0.9 | 255.255.255.0 | 200.0.0.1 |

### 📝 **3.2 Justification for IP Addressing**
- **Class B (Floors 1-2)** ensures large address space for growth and security.
- **Class C (Floors 3-7)** provides optimized allocation for public connectivity.

---

## 🚀 **4. Routing Strategy for Inter-Floor Communication**
### 🔀 **4.1 Dynamic Routing Approach**
#### 📡 **4.1.1 OSPF (Open Shortest Path First)**
✅ **Justification:**
- **Fast Convergence:** Quickly updates routes when network changes occur.
- **Scalability:** Supports multi-floor environments efficiently.
- **Optimal Routing:** Uses the Dijkstra algorithm to determine the best path.

### 🖥 **4.2 Network Devices and Placement**
- **Switches:** Layer-2 managed switches per floor for traffic control.
- **Routers:** Dedicated routers per floor + core router in the server room.
- **Access Points:** Deployed for seamless Wi-Fi coverage.

### 🎯 **4.3 Default Gateways**
| Floor  | Default Gateway |
|--------|----------------|
| Floor 1 | 172.16.0.1 |
| Floor 2 | 172.17.0.1 |
| Floor 3 | 196.0.0.1 |
| Floor 4 | 197.0.0.1 |
| Floor 5 | 198.0.0.1 |
| Floor 6 | 199.0.0.1 |
| Floor 7 | 200.0.0.1 |

---

## 📡 **5. Network Diagram**
```
Core Router (Server Room)
   |
   |-- Floor 1 Router (172.18.0.1) -- Ring Topology (172.16.0.0/16)
   |-- Floor 2 Router (172.18.0.2) -- Ring Topology (172.17.0.0/16)
   |-- Floor 3 Router (192.0.0.2) -- Mesh Topology (196.0.0.0/24)
   |-- Floor 4 Router (193.0.0.2) -- Mesh Topology (197.0.0.0/24)
   |-- Floor 5 Router (194.0.0.2) -- Mesh Topology (198.0.0.0/24)
   |-- Floor 6 Router (195.0.0.2) -- Mesh Topology (199.0.0.0/24)
   |-- Floor 7 Router -- Mesh Topology (200.0.0.0/24)
```

---

## 🎯 **6. Conclusion**
This network design ensures **efficient, scalable, and fault-tolerant communication**. The combination of **ring and mesh topologies**, structured IP addressing, and **OSPF dynamic routing** provides a **robust and reliable infrastructure**.

---

## 🔥 **7. Recommendations**
✅ Implement **redundant power supplies** for routers.
✅ Use **QoS policies** to prioritize critical traffic.
✅ Regularly update **firewalls and security protocols**.
✅ Monitor network performance with **SNMP-based tools**.

---

_Designed by Sajal Kanwal_ 🚀

