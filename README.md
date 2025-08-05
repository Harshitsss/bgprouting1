# 🔐 Network Security & Routing Project – Cisco Packet Tracer

This project contains two key components focused on **firewall configuration** and **routing protocols** using Cisco Packet Tracer:

1. 🛡️ Built-In Firewall Configuration on a PC
2. 🌐 BGP Routing Between Multiple Autonomous Systems

Each configuration is saved in a separate `.pkt` file and serves as a practical simulation for learning and demonstration purposes.

---

## 📁 Files in This Repository

| File Name                   | Description                                                 |
|-----------------------------|-------------------------------------------------------------|
| `PC_BuiltIn_Firewall.pkt`   | Demonstrates firewall configuration using PC's built-in firewall |
| `BGP_Routing.pkt`           | Demonstrates BGP routing between 3 different autonomous systems |

---

## 🛡️ Built-In Firewall on PC

This setup demonstrates how to configure the **built-in firewall** on a PC in Cisco Packet Tracer to control incoming and outgoing traffic.

### 🧱 Network Setup

- 💻 PC with firewall enabled
- 🌐 Server (for HTTP/FTP testing)
- 💻 Other PCs (for traffic testing)
- 🔀 Switch for LAN connectivity

### 🔧 Firewall Settings (Configured on PC)

- Go to the PC → **Config Tab** → **Firewall**
- Enable or disable access to specific ports/services

| Service | Port | Status     |
|---------|------|------------|
| HTTP    | 80   | ✅ Allowed  |
| FTP     | 21   | ❌ Denied   |
| ICMP    | —    | ❌ Denied   |

### 🧪 Testing Instructions

- Use other PCs to ping the firewall-enabled PC (ICMP)
- Try accessing `http://<PC-IP>` (HTTP)
- Attempt FTP connection (if server provides it)
- Observe what traffic is allowed or blocked

### 🎯 Learning Outcomes

- Understand host-level traffic control using built-in firewalls
- Learn to block/allow services by port number
- Simulate a real-world client firewall setup

---

## 🌐 BGP Routing Configuration

This part of the project demonstrates how to configure **BGP (Border Gateway Protocol)** for routing between multiple autonomous systems.

### 🧱 Network Setup

- 3 Routers (each in a separate AS)
- PCs or networks behind each router
- Serial or Ethernet links for router interconnection

| Router | AS Number |
|--------|-----------|
| R1     | 65001     |
| R2     | 65002     |
| R3     | 65003     |

### 🔧 BGP Configuration Example

#### 🔹 Router R1 (AS 65001)
```bash
router bgp 65001
  neighbor 10.0.0.2 remote-as 65002
  network 192.168.1.0 mask 255.255.255.0
