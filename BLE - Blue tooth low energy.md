## **Bluetooth Low Energy (BLE) Overview**

- **Introduced in Bluetooth 4.0**  
    BLE was added in the **Bluetooth 4.0** specification to enable wireless communication for low-power, short-range devices (e.g., wearables, health monitors).
    
- **Designed for Low Power**
    - Optimized for minimal power usage, making it ideal for battery-powered devices.
    - Significantly lower energy consumption compared to **Classic Bluetooth**.

---

## **Device Roles**

### **Central**

- The **initiator** of the communication.
- Scans for and connects to peripherals.
- Typically a smartphone, computer, or hub.

### **Peripheral**

- The **advertiser** of data.
- Waits for connection requests from a central device.
- Usually small, power-constrained devices (e.g., heart rate monitors, smartwatches).

---

## **Power Efficiency**

- BLE's main method of saving energy:
    > Devices **remain in sleep mode** and **only wake up** to transmit or receive data.  
    > This leads to **very short active periods**, reducing overall energy consumption.

---

## **GATT – Generic Attribute Profile**

- Defines how **data is structured and exchanged** in BLE.
- Based on a **hierarchy** of services and characteristics:
    - **Service**: A collection of related characteristics (e.g., Heart Rate Service).
    - **Characteristic**: A single data point (e.g., heart rate measurement).

---

## **Other Key Features**

- **128-bit UUIDs (Universally Unique Identifiers)**
    - Used to identify services and characteristics.
    - Custom services use full 128-bit UUIDs; standard ones use 16-bit short forms.
- **Lower Data Rate than Classic Bluetooth**
    - BLE prioritizes energy efficiency and latency over throughput.
    - Suitable for small bursts of data, not continuous streaming.