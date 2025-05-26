## 📘 Overview
- **CAN** is a robust vehicle bus standard designed to allow microcontrollers and devices to communicate with each other in applications without a host computer.
- Commonly used in automotive and industrial systems.

---

## 🧰 Stuff Needed
- 2x Arduino UNO or Nano
- 2x MCP2515 CAN Bus modules with TJA1050 transceiver.
- Jumper wires
- Common GND between devices

---

## ⚙️ Wiring (for both Arduinos)
### Arduino to MCP2515 Module:
- **VCC** → **5V**  
- **GND** → **GND**  
- **CS** → **D10**  
- **S0** (SCK) → **D13**  
- **SI** (MOSI) → **D11**  
- **SO** (MISO) → **D12**  
- **INT** → **D2**

### Between MCP2515 Modules:
- **CAN_H** ↔ **CAN_H**
- **CAN_L** ↔ **CAN_L**

> ✅ Make sure to connect both modules to a **common GND**.

---

## 🧪 Testing Setup
- Install the [**mcp_can** library](https://github.com/coryjfowler/MCP_CAN_lib) by Cory J. Fowler via Arduino Library Manager.
- Load the `send` sketch on one Arduino, and `receive` sketch on the other.

---

## 📤 Send Example (Sender Arduino)
```cpp
#include <mcp_can.h>
#include <SPI.h>

const int SPI_CS_PIN = 10;
MCP_CAN CAN(SPI_CS_PIN);

void setup() {
  Serial.begin(115200);
  while (CAN_OK != CAN.begin(CAN_500KBPS)) {
    Serial.println("CAN BUS init Failed");
    delay(100);
  }
  Serial.println("CAN BUS init OK!");
}

void loop() {
  byte data[] = {0x01, 0x02, 0x03, 0x04};
  CAN.sendMsgBuf(0x70, 0, 4, data);
  Serial.println("Message sent");
  delay(1000);
}
```

## 📥 Receive Example (Receiver Arduino)

```cpp
#include <mcp_can.h>
#include <SPI.h>

const int SPI_CS_PIN = 10;
MCP_CAN CAN(SPI_CS_PIN);

void setup() {
  Serial.begin(115200);
  while (CAN_OK != CAN.begin(CAN_500KBPS)) {
    Serial.println("CAN BUS init Failed");
    delay(100);
  }
  Serial.println("CAN BUS init OK!");
}

void loop() {
  if (CAN_MSGAVAIL == CAN.checkReceive()) {
    byte len = 0;
    byte buf[8];
    CAN.readMsgBuf(&len, buf);
    Serial.print("Received: ");
    for (int i = 0; i < len; i++) {
      Serial.print(buf[i], HEX);
      Serial.print(" ");
    }
    Serial.println();
  }
}

```



![[Pasted image 20250525222108.png]]
![[Pasted image 20250525222120.png]]
![[Pasted image 20250525222130.png]]
![[Pasted image 20250525222147.png]]