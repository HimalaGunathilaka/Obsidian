## HomePlug
- **Description**: Power line communication protocol that uses existing electrical wiring to transmit data.
- **Key Features**:
  - Data is **broadcast across the power line network**, but only the intended recipient processes the signal.
  - **Modulated data** signal is carried alongside standard 50Hz or 60Hz AC power, allowing devices to communicate without interfering with regular electrical appliances.
  - Uses **Carrier Sense Multiple Access (CSMA)** to avoid data collisions and ensure efficient communication.
  - Devices have unique **identifiers** (MAC addresses) to ensure targeted communication.
- **Why it's Special**: Efficient use of existing infrastructure (powerlines) and does not require additional wiring. **Cost-effective for home networking**.

---

## Zigbee SE (Smart Energy)
- **Description**: A low-power, low-data-rate protocol designed for **smart grid** and **energy monitoring**.
- **Key Features**:
  - Primarily **event-driven**, optimized for energy management and monitoring.
  - Uses a **mesh network** topology for flexible and scalable communication.
  - Suitable for **smart energy applications**, allowing devices to report energy usage data or adjust energy consumption.
  - **Low power** consumption makes it ideal for battery-powered devices.
- **Why it's Special**: Focuses on **energy efficiency** and supports scalable, low-power communication in energy monitoring and smart grid systems.

---

## Dash7
- **Description**: A long-range, low-power, wireless communication protocol designed for the **Internet of Things (IoT)**.
- **Key Features**:
  - **IEEE 802.15.4**-compliant, operating in the sub-1 GHz and 2.4 GHz bands.
  - Designed for low-power, low-data-rate applications, especially those requiring **remote sensors** and **asset tracking**.
  - Supports **long-range communication** (up to 10 km in open environments).
  - Includes features like **frequency hopping** and **TDMA** (Time Division Multiple Access) to optimize communication.
- **Why it's Special**: **Long-range capabilities** and low power consumption, making it ideal for **remote sensing** and **asset tracking**.

---

## Zigbee
- **Description**: A widely used low-power, low-data-rate wireless protocol for **personal area networks (PANs)**.
- **Key Features**:
  - Operates in the **2.4 GHz** frequency band.
  - **Mesh network** topology, allowing devices to relay data across the network.
  - **Event-driven** and optimized for **short-range** communication.
  - Designed for applications like **home automation**, **security**, and **sensor networks**.
- **Why it's Special**: Known for **interoperability** and low-power, low-latency communication, especially in smart homes and automation.

---

## WirelessHART
- **Description**: A wireless protocol designed for **industrial automation**, enabling communication between devices in hazardous or difficult-to-reach environments.
- **Key Features**:
  - Operates in the **2.4 GHz** frequency band and supports **mesh networking**.
  - Optimized for **reliable, secure, real-time data transmission** in industrial environments.
  - **Self-healing** network, where devices can route data through other nodes if one device fails.
  - Includes **security features** like data encryption.
- **Why it's Special**: Reliable and **secure communication** for industrial automation, especially in **hazardous** environments.

---

## HomePlug AV
- **Description**: An updated version of **HomePlug**, providing high-speed data transfer over existing powerlines.
- **Key Features**:
  - **High-speed data transmission** (up to 500 Mbps).
  - **Supports QoS (Quality of Service)** to prioritize certain types of traffic (e.g., video, gaming).
  - Uses **powerline wiring** for **data transmission** in homes or businesses without requiring new cabling.
- **Why it's Special**: **High-speed internet** over powerlines, convenient for homes with poor Wi-Fi coverage.

---

## IEEE 802.15.4
- **Description**: A low-power, low-data-rate wireless communication standard, used as the basis for protocols like Zigbee, Thread, and WirelessHART.
- **Key Features**:
  - Operates in multiple frequency bands (**868 MHz**, **915 MHz**, **2.4 GHz**).
  - Suitable for **low-power, low-rate communication** in IoT and sensor networks.
  - Provides reliable, **secure communication** with **mesh networking** support.
- **Why it's Special**: Serves as the foundation for many popular IoT protocols, offering flexible communication tailored for low-power devices.

---

## Dash7 (Cont'd)
- **Key Points**:
  - **Frequency Hopping**: Helps avoid interference and allows multiple devices to communicate simultaneously.
  - **Long-Range Communication**: Ideal for applications that require devices to communicate over significant distances.
  - **Optimized for IoT**: Excellent for remote sensing and tracking applications due to its low power consumption and extended range.
  
---

# Key Differences:
- **Zigbee SE** focuses on **smart energy applications** with an **event-driven** approach.
- **Dash7** is designed for **long-range** communication and excels in applications requiring remote sensing or asset tracking.
- **WirelessHART** is tailored for **industrial automation** and works in **hazardous environments**.
- **HomePlug AV** is designed for **high-speed** networking over existing powerlines in home and office environments.

---
# 📡 Wireless Communication Protocols for IoT & Networking

This note summarizes key protocols discussed in the context of IoT, LPWANs, and general wireless networking.

---

## 🔌 G.9959 (ITU-T Standard)

### Overview
- **Designed for**: Low-power wireless communication in home automation.
- **Use cases**: Smart home devices (e.g., Z-Wave).
- **Topology**: Mesh and star.
- **Features**:
  - Range: ~100 meters (indoors).
  - Frequency: Sub-GHz (e.g., 868/915 MHz).
  - Low data rate, low latency.
  - Power-efficient.

### Notable Uses
- **Z-Wave** is built on this protocol.

---

## 📶 Zigbee & Z-Wave (Mentioned)

### Zigbee (based on IEEE 802.15.4)
- **Spectrum**: 2.4 GHz (global).
- **Topology**: Mesh.
- **Use case**: Smart homes, lighting, sensors.
- **Good for**: Short range, low power, high interoperability.

### Z-Wave (based on G.9959)
- **Spectrum**: Sub-GHz.
- **Topology**: Mesh.
- **Use case**: Home automation.
- **Range**: Better wall penetration than Zigbee.

---

## 📱 LTE-Advanced (LTE-A)

### Overview
- **Evolution of LTE** for higher speeds and better spectral efficiency.
- **Not primarily IoT**, but supports:
  - M2M (Machine-to-Machine).
  - NB-IoT (Narrowband IoT) extensions.

### Key Features
- **Carrier Aggregation**: Combines multiple bands.
- **MIMO**: Multiple antennas for faster speeds.
- **Peak speeds**: Up to 3 Gbps DL, 1.5 Gbps UL.
- **Latency**: ~10 ms or lower.
- **Backward compatibility**: Works with LTE networks.

### Why “Long Term Evolution”?
- LTE was designed to evolve over time using existing infrastructure.
- **"Advanced"** = a major enhancement within the same family (3GPP Rel. 10+).

---

## 🌍 Weightless Protocol

### Overview
- **Open, royalty-free LPWAN protocol** for IoT.
- Operates in **sub-GHz** unlicensed spectrum (868/915 MHz).
- Designed for **long-range, low-power, low-cost** deployments.

### Key Features
- Range: 2–10 km+ (rural), less in urban areas.
- Battery life: 5–10 years.
- AES-128 encryption.
- Star topology.
- Bidirectional communication (Weightless-P).
- Supports thousands of nodes.

### Variants
| Version        | Spectrum         | Directionality | Use Case                    |
|----------------|------------------|----------------|-----------------------------|
| Weightless-W   | TV White Space   | Bidirectional  | Rural, long-range           |
| Weightless-N   | Narrowband ISM   | Uplink only    | Simple sensor nodes         |
| Weightless-P   | Sub-GHz ISM      | Bidirectional  | Industrial, flexible IoT    |

### Compared to IEEE 802.15.4
- ✅ Longer range
- ✅ Lower frequency = better penetration
- ❌ No mesh support
- ❌ Smaller ecosystem

---

## 📘 IEEE 802.15.4 (Baseline for Zigbee, Thread)

### Overview
- **Standard for low-rate wireless personal area networks (LR-WPANs)**.
- **Used in**: Zigbee, Thread, 6LoWPAN, etc.
- **Spectrum**: 2.4 GHz, 868/915 MHz.
- **Data rate**: Up to 250 kbps.
- **Topology**: Mesh or star.
- **Range**: Short (10–100 meters).
- **Power**: Very low.

---

## 🧠 Summary Comparison Table

| Protocol        | Range         | Power Use | Spectrum   | Topology   | IoT Fit | Notes                              |
|-----------------|---------------|-----------|------------|------------|---------|------------------------------------|
| **G.9959**      | ~100m         | Low       | Sub-GHz    | Mesh/star  | ✅ Yes  | Used in Z-Wave                     |
| **Zigbee**      | 10–100m       | Very Low  | 2.4 GHz    | Mesh       | ✅ Yes  | Based on IEEE 802.15.4             |
| **LTE-A**       | 1–10 km+      | High      | Licensed   | Cellular   | ⚠️ Partial | Great for high-bandwidth apps     |
| **Weightless**  | 2–10 km+      | Very Low  | Sub-GHz    | Star       | ✅ Yes  | Open LPWAN, long battery life      |
| **802.15.4**    | 10–100m       | Very Low  | 2.4 GHz    | Mesh/star  | ✅ Yes  | Foundation for Zigbee/Thread       |

---

## 🧩 See Also
- [[LoRaWAN]]
- [[NB-IoT]]
- [[Thread Protocol]]
- [[Wireless Protocol Selection for IoT]]

# IoT Networking Protocols Summary

## 📡 DECT/ULE (Digital Enhanced Cordless Telecommunications / Ultra Low Energy)

### Key Features
- **Origin**: Based on the DECT standard (used in cordless phones).
- **ULE**: Tailored for ultra-low power IoT devices.
- **Frequency**: Uses a **dedicated sub-GHz band** (1880–1900 MHz in many regions).
- **Topology**: One **master (base station)** and multiple **slave (device)** nodes.
- **Range**: Long indoor range (~300 meters line-of-sight).
- **Coexistence**: Operates in a **less crowded band**, avoids Wi-Fi/Bluetooth interference.
- **Security**: End-to-end encryption built-in.

### Advantages
- Not susceptible to 2.4GHz congestion.
- Reliable for **home automation and sensors**.
- Allows direct audio + data streaming.

---

## 🌳 RPL (Routing Protocol for Low-Power and Lossy Networks)

### Overview
- Designed for **IPv6-based** networks in constrained environments.
- Forms a **DODAG** (Destination-Oriented Directed Acyclic Graph).
- Each DODAG has a **root** node (typically the gateway or sink).

### Modes
- **Storing Mode**: Nodes store downward routes (routing tables).
- **Non-Storing Mode**: Only the root stores full topology and uses **source routing**.

### Packet Flow: A to B
- A sends a packet → upward via parent(s) → root (Y) → down to B
- Depending on mode:
  - **Storing**: Nodes along the way know how to reach B.
  - **Non-Storing**: Root sends full path to B in the packet header.

---

## 🔁 Routing Behavior

### Do Nodes Know Their Children?

| Mode               | Knows Children? | How Downward Routing Works                     |
|--------------------|------------------|------------------------------------------------|
| **Storing Mode**   | ✅ Yes           | Each node stores routes to its descendants.   |
| **Non-Storing Mode** | ❌ No           | Only the root stores routes and uses source routing. |

### Example Path (A → B with root Y):

- **Storing**:  
  `A → parent → ... → common ancestor → ... → B`

- **Non-Storing**:  
  `A → Y (root)` → Y inserts path to B → `Y → ... → B`

---

## 🧠 Summary Table

| Feature                  | DECT/ULE                           | RPL (Storing)                    | RPL (Non-Storing)             |
|--------------------------|------------------------------------|----------------------------------|-------------------------------|
| Frequency Band           | 1880–1900 MHz                      | Any (RPL is protocol, not radio) | Any                           |
| Topology                 | Master-slave (star)                | DODAG (tree)                     | DODAG (tree)                  |
| IP Support               | ❌ (typically not IP-based)         | ✅ IPv6                           | ✅ IPv6                        |
| Route Memory (Nodes)     | ❌ N/A                              | ✅ Yes (stores children)         | ❌ No                          |
| Source Routing           | ❌                                  | ❌                                | ✅ Yes                         |
| Suited For               | Home automation (sensor/audio)     | Wireless sensor networks         | Low-mem IoT networks          |

---

## 📌 Notes
- DECT/ULE and RPL solve **different problems**:
  - DECT/ULE is a **radio + MAC** layer protocol.
  - RPL is a **network layer routing** protocol over IPv6.
- DECT/ULE typically does **not use IP**, while RPL is part of **IPv6-based stacks** (like 6LoWPAN).

# Networking Protocols Summary

## 1. **RPL (Routing Protocol for Low-Power and Lossy Networks)**

- **Use Case**: Primarily for **low-power and lossy networks (LLNs)**, such as **IoT** and **WSNs**.
- **Structure**: **DODAG** (Destination Oriented Directed Acyclic Graph) — **tree-like** topology.
- **Routing Style**: **Unicast**; each node has a **single preferred parent**.
- **Key Features**:
  - Supports **multi-hop communication**.
  - Supports **simple network configurations** for devices with low power and memory.
  - **Quality of Service (QoS)**: Nodes select parents based on metrics such as **ETX** (Expected Transmission Count).
  - **Limitations**: Not ideal for highly dynamic or lossy environments.

### Pros:
- Simple and efficient for static or semi-static networks.
- Well-suited for **IoT** devices with low resources.

### Cons:
- Single parent makes it less robust in dynamic, unreliable environments.
- Susceptible to **parent failures** or network topology changes.

---

## 2. **CORPL (Contiki Opportunistic RPL)**

- **Use Case**: Improved RPL variant for **low-power and lossy networks (LLNs)** with more **dynamic routing**.
- **Structure**: Based on **RPL's DODAG**, but adds **opportunistic routing**.
- **Routing Style**: **Opportunistic**; multiple candidate parents (coordination set).
- **Key Features**:
  - **Coordination Set** (CS) allows nodes to forward packets opportunistically.
  - **Broadcasting** to multiple potential parents increases **reliability** and robustness.
  - **Token-based mechanism** ensures only one node forwards the packet to prevent duplicates.
  - **Higher fault tolerance** and **better load balancing** than traditional RPL.

### Pros:
- Increased **resilience** in dynamic and lossy environments.
- Better handling of **network failures**.

### Cons:
- Slightly more **complex** compared to traditional RPL due to opportunistic forwarding.

---

## 3. **CARP (Channel-Aware Routing Protocol)**

- **Use Case**: Primarily for **underwater acoustic sensor networks (UWSNs)** or **wireless sensor networks (WSNs)**, where **link quality** is highly variable.
- **Structure**: Based on **hop-by-hop** routing, but **aware of channel conditions** (e.g., signal-to-noise ratio, link quality).
- **Routing Style**: **Hop-by-hop** with **link quality estimation**; avoids poor links and energy waste.
- **Key Features**:
  - **Channel awareness** allows nodes to select paths based on link quality.
  - Dynamic routing decisions based on **real-time link measurements**.
  - **Flat routing**: No global routing table; decisions are made on-the-fly.
  - Efficient in **unreliable** environments with **high packet loss**.

### Pros:
- **Energy-efficient** by avoiding poor links.
- **Improved reliability** in dynamic and harsh environments (e.g., underwater).
- **Scalable** for large networks.

### Cons:
- May not be directly applicable to **terrestrial** IoT networks.
- Requires continuous monitoring of **channel conditions**, which may incur some overhead.

---

## Comparison: RPL vs CORPL vs CARP

| Feature               | **RPL**                      | **CORPL**                      | **CARP**                          |
|----------------------|------------------------------|--------------------------------|-----------------------------------|
| **Use Case**         | Low-power IoT, WSNs          | LLNs with dynamic routing     | Underwater and harsh environments |
| **Routing Structure**| Tree-based (DODAG)           | Mesh-like (DODAG + Opportunistic) | Hop-by-hop, channel-aware        |
| **Forwarding Style** | Unicast (single parent)      | Opportunistic (multiple parents) | Hop-by-hop with link quality     |
| **Resilience**       | Moderate                     | High                           | High                              |
| **Energy Efficiency**| Moderate                     | Higher                         | Very high                         |
| **Best For**         | Static or semi-static IoT networks | Dynamic and lossy IoT networks | Underwater or harsh, dynamic environments |

---

## Conclusion

- **RPL**: Best for static, low-power IoT networks where the topology doesn’t change frequently.
- **CORPL**: Ideal for **dynamic networks** with high link variability, where **reliability** and **fault tolerance** are essential.
- **CARP**: Designed for **underwater acoustic sensor networks** or **harsh environments**, focusing on **energy efficiency** and **channel awareness**.

