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
### Packet structure
![[Pasted image 20250526215015.png]]
- **Preamble**
    - **Purpose**: Helps the receiver detect the beginning of a packet.
    - **Details**: A sequence of up-chirps that allows the receiver’s automatic gain control (AGC) to settle and synchronize with the incoming signal.
    - **Configurable Length**: Default is usually 8 symbols, but it can vary based on configuration.
    
- **Sync Word**
    - **Purpose**: Differentiates LoRaWAN packets from other LoRa-based systems.
    - **Details**: A special sequence following the preamble; LoRaWAN uses specific sync words (typically `0x34` for public networks).
    - **Function**: Allows receivers to filter out irrelevant packets.
    
- **Down-Chirp** (a.k.a. Start Frame Delimiter)
    - **Purpose**: Marks the transition from preamble to the actual packet data.
    - **Details**: A single down-chirp (frequency sweep downwards) that signals the end of the preamble and enables precise timing synchronization.
- **Header**
    - **Purpose**: Provides information about the payload and transmission settings.
    - **Details**:
        - May include payload length, coding rate, and CRC presence.
        - In **explicit mode**, the header is included.
        - In **implicit mode**, the header is omitted to save airtime (both ends must be pre-configured).
    
- **Payload**
    - **Purpose**: The actual data being transmitted.
    - **Details**:
        - Contains the MAC header (MHDR), MAC payload (which includes Frame Header (FHDR), Frame Port, and FRMPayload), and MIC (message integrity code).
        - Encrypted using AES encryption for confidentiality and integrity.
    
- **CRC (Cyclic Redundancy Check)**
    - **Purpose**: Ensures data integrity.
    - **Details**:
        - Optional in the header (based on mode).
        - Always included in the physical layer trailer to verify correct packet reception.
        - Used to detect errors in transmission.
    
---
## Lab
- Stuff need : 
	esp32 ---> 2 
	LoRa Ra-02 SX1278 Module ---> 2 
	![[Pasted image 20250523194226.png]]
	Jumper wires
- Connect the esp32 to the lora module using diagram shown below.
![[Pasted image 20250523193824.png]]
>Note
- The esp32 works under 3.3V and the LoRa modules works under 3.3V as well. It is recommend to use esp32 here, since something like Arduino uno boards use 5V, the logic levels it used may get 5V as well. (Not suitable for the LoRa module.)


### ~={purple}Sender code=~
- Here is a simple arduino code that uses LoRa library package to send "hello".
```ino 
#include <LoRa.h>
#define SS 2
#define RST 33
#define DIO0 32
String data = "hello";
void setup()
{
  Serial.begin(9600);
  while (!Serial);
  Serial.println("Sender Host");
  LoRa.setPins(SS, RST, DIO0);
  if (!LoRa.begin(433E6)) {
    Serial.println("LoRa Error");
    delay(100);
    while (1);
  }
}
void loop()
{
  Serial.print("Sending Data: ");
  Serial.println(data);
  LoRa.beginPacket();
  LoRa.print(data);
  LoRa.endPacket();
  delay(1000);
}
```
### ~={purple}Receiver=~
- The message is being captured in here.
```ino
#include <LoRa.h>
#define SS 5
#define RST 14
#define DIO0 2
void setup() {
  Serial.begin(9600);
  while (!Serial);
  Serial.println("Receiver Host");
  LoRa.setPins(SS, RST, DIO0);
  if (!LoRa.begin(433E6)) {
    Serial.println("LoRa Error");
    while (1);
  }
}

void loop() {
  int packetSize = LoRa.parsePacket();
  if (packetSize) {
    Serial.print("Receiving Data: ");
    while (LoRa.available()) {
      String data = LoRa.readString();
      Serial.println(data);
    }
  }
}
```
