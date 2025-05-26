## 📘 Overview

- **CAN** (Controller Area Network) is a robust vehicle bus standard designed to allow microcontrollers and devices to communicate with each other in applications without a host computer.
    
- Think of it as the _neural network_ that connects the Electronic Control Units (ECUs).
    

![[Pasted image 20250526201353.png]]

- Commonly used in automotive and industrial systems.
    
- CAN uses a twisted pair of wires (CAN Low and CAN High) for transmission. Electromagnetic interference affects both wires equally, minimizing transmission errors.
    

---

## 🧱 CAN Frame

![[Pasted image 20250526210833.png]]

- **SOF (Start of Frame)**: A dominant ‘0’ that signals the start of a frame and notifies other nodes that communication is beginning.
    
- **ID (Identifier)**: Specifies the message's purpose and source. It also determines message priority—lower ID means higher priority.
    
- **RTR (Remote Transmission Request)**: Indicates whether the frame is requesting data or sending it.
    
- **Control**: Contains:
    
    - **IDE (Identifier Extension Bit)** – dominant ‘0’ for standard 11-bit IDs.
        
    - **DLC (Data Length Code)** – a 4-bit field that defines the number of data bytes (0–8).
        
- **Data**: Carries up to 8 bytes of actual message data.
    
- **CRC (Cyclic Redundancy Check)**: Used for error detection.
    
- **ACK (Acknowledgement Slot)**: Indicates whether the message was received correctly by any node.
    
- **EOF (End of Frame)**: Marks the end of the message.
    

---

## 🧰 Hardware for a Demo

- 2× Arduino UNO or Nano
    
- 2× MCP2515 CAN Bus Modules with TJA1050 Transceiver
    
- Jumper wires
    

> 🔧 The MCP2515 module includes both the transceiver and the CAN controller.

---

## ⚙️ Wiring (for both Arduinos)

### Arduino to MCP2515 Module

- **VCC** → **5V**
    
- **GND** → **GND**
    
- **CS** → **D10**
    
- **SCK** → **D13**
    
- **MOSI** → **D11**
    
- **MISO** → **D12**
    
- **INT** → **D2**
    

### Between MCP2515 Modules

- **CAN_H** ↔ **CAN_H**
    
- **CAN_L** ↔ **CAN_L**
    

> ✅ Ensure **common GND** between both modules.
---

## 🧪 Testing Setup

- Install the [**mcp_can** library](https://github.com/coryjfowler/MCP_CAN_lib) by _Cory J. Fowler_ via the Arduino Library Manager.
    
- Upload the `send` sketch to one Arduino and the `receive` sketch to the other.
    

---

## 📤 Sender Code (Arduino)
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
---
## 📥 Receive Code (Arduino)

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

---
>Below is the CAN High and CAN Low signal line:
![[Pasted image 20250525222120.png]]

>MCP2515 module
![[Pasted image 20250525222130.png]]

>Connection diagram between CAN module and Arduino UNO:
![[Pasted image 20250526211342.png]]

>Real-world connection setup:
![[Pasted image 20250525222108.png]]
---

_Reference_ : https://lastminuteengineers.com/mcp2515-can-module-arduino-tutorial/




_By_ : M.H.S. Gunathilaka 220199L