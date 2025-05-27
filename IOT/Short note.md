- Name of the wifi -> __SSID__ 
- MAC address -> __BSSID__ 
- __Channel__ = The frequency is being divided into channels to use separately. By using it like that multiple routers can communicate in the same area of business.
- _Hard coding the wifi initials_ = Don't do that,
		Make a access point.
- Modes in esp32
	- Active
	- Deep-sleep
	- Light-sleep
![[Pasted image 20250518205136.png]]
- CPU pause -> Means the runned instructions retains and will start again when depaused.  
- ESP.deepsleep(5e6) -> $5 * 10^6$ milliseconds, (0 will be sleeping forever.)
---
## Modbus

**Modbus** 
For industrial automation systems. It has become one of the most widely used protocols for connecting industrial electronic devices.

- __Open protocol__  
  Modbus is an open standard, meaning it is publicly available and can be freely used and implemented by anyone. This openness contributed to its wide adoption in the industrial world.

- __Oldest SCADA protocol__  
  Modbus is one of the oldest and most reliable communication protocols still in use today, especially in **Supervisory Control and Data Acquisition (SCADA)** systems. Its simplicity and robustness make it ideal for industrial environments.

- __TCP/IP connection__  
  The **Modbus TCP/IP** variant allows devices to communicate over standard Ethernet networks. This enables easier integration with modern IT infrastructure while retaining the simplicity of the Modbus protocol.

- __Serial port and Ethernet__  
  Modbus supports multiple physical communication layers:
  - **Modbus RTU**: Uses serial communication (RS-232, RS-485) and is compact and efficient for point-to-point or multi-drop setups.
  - **Modbus ASCII**: Similar to RTU but data is encoded in ASCII characters, which makes it easier to debug.
  - **Modbus TCP**: Operates over Ethernet using TCP/IP, offering faster communication and longer distance coverage.

### Summary

| Feature             | Details                                                    |
| ------------------- | ---------------------------------------------------------- |
| Type                | Master/Slave or Client/Server                              |
| Transport Layers    | Serial (RS-232/485), TCP/IP (Ethernet)                     |
| Use Cases           | SCADA, PLCs, Sensors, HMIs                                 |
| Protocol Simplicity | High – easy to implement                                   |
| Data Model          | Coils, Discrete Inputs, Input Registers, Holding Registers |
- ~={red}It is in application layer.=~

## 🔄 What is a Schmitt Trigger?

A **Schmitt Trigger** is a special type of input circuit used to **clean up noisy signals** and prevent **false triggering** by introducing **hysteresis**.

---

## ⚡ Why is it Needed?

Digital inputs expect a clean HIGH or LOW signal. But in real life, analog signals (like from sensors or buttons) often:

- Have **slow edges** (don’t switch instantly)
- Contain **noise or ripple**

This can cause multiple unwanted transitions ("bouncing" or false triggering).

---

## ✅ What a Schmitt Trigger Input Does:

It ensures **clean digital transitions** by:
- Requiring the input to **cross two different voltage thresholds**:
    - One for going from LOW to HIGH
    - One for going from HIGH to LOW
        

This is called **hysteresis**.



