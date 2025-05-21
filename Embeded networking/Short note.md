- **Heterogeneous hardware** means using **different types of hardware components**, each specialized for certain tasks, **working together in one system**.

| **Type of Networking**    | **Circuit Switching**                        | **Packet Switching**                        |
| ------------------------- | -------------------------------------------- | ------------------------------------------- |
| **Physical Path**         | Physical path between source and destination | No physical path                            |
| **Path Usage**            | All packets use the same path                | Packets travel independently                |
| **Bandwidth Reservation** | Reserve the entire bandwidth in advance      | Does not reserve the bandwidth              |
| **Bandwidth Wastage**     | Bandwidth wastage                            | No bandwidth wastage                        |
| **Transmission Method**   | No Store and forward transmission            | ==Supports store and forward transmission== |
- **Store and forward** is an important technique in networking because it improves the reliability, flexibility, and efficiency of data transmission.
![[Pasted image 20250501103921.png]]

- **General term**: A **PDU** is a generic term used to refer to a unit of data at any layer in the OSI model or the TCP/IP stack. At each layer, the data is called by a different name (like a **frame**, **packet**, **segment**, etc.), but they all fit under the umbrella term "PDU."
	- - **Physical Layer**: Bits
	- **Data Link Layer**: Frame
	- **Network Layer**: Packet
	- **Transport Layer**: Segment (for TCP) or Datagram (for UDP)
	- **Application Layer**: Data

## TCP - Transmission control protocol
![[Pasted image 20250501114056.png]]
- 3-Way handshake
![[Pasted image 20250501120245.png]]
---
### ✅ TCP 3-Way Handshake (Connection Start)
1. **SYN → (Client → Server)**  
   Client: "Start connection, here's my sequence number."

2. **SYN-ACK ← (Server → Client)**  
   Server: "Got it. Here's mine."

3. **ACK → (Client → Server)**  
   Client: "Acknowledged."

✅ **Connection Established**

---

### ❌ TCP 4-Way Handshake (Connection End)
1. **FIN → (Client → Server)**  
   Client: "I'm done sending."

2. **ACK ← (Server → Client)**  
   Server: "Got your FIN."

3. **FIN ← (Server → Client)**  
   Server: "I'm done too."

4. **ACK → (Client → Server)**  
   Client: "Acknowledged."

✅ **Connection Closed**
