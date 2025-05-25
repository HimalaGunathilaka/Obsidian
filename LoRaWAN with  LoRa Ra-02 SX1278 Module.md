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
```

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
