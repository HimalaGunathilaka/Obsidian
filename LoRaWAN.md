## 🌐 Introduction to LoRaWAN

### 📘 What is LoRaWAN?

- **LoRaWAN** stands for **Long Range Wide Area Network**.
- It's a **Low-Power, Wide-Area Networking (LPWAN)** protocol built on top of **LoRa (Long Range)** modulation.
- Designed for **IoT applications** that require devices to communicate over long distances with minimal power consumption.
- Operates in **unlicensed frequency bands** (e.g., 433 MHz, 868 MHz, 915 MHz depending on region).

---

### 🧠 Key Concepts

- **LoRa** handles the physical layer (modulation).
- **LoRaWAN** defines the communication protocol and system architecture.
- Devices communicate with **gateways**, which forward packets to **network servers**.
- Supports **bi-directional communication**, **adaptive data rates**, and **end-to-end encryption**.

---

### 📦 Architecture

```text
+------------+       +-----------+       +-----------------+
|   End Node | <---> |  Gateway  | <---> |  Network Server |
+------------+       +-----------+       +-----------------+
                                      ↕
                              +----------------+
                              | Application Srv |
                              +----------------+
