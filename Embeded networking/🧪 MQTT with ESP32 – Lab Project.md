## 📘 Overview
- **MQTT** stands for **Message Queuing Telemetry Transport**.
- It's a **session layer protocol** in the **OSI model**, built on top of **TCP/IP**.
- MQTT is lightweight, ideal for **IoT** devices like the ESP32.

---

## 🧰 Stuff Needed

### 🔌 Hardware
- ESP32 development board  *(Its very handy to have and its easily found in CSE labs)*
- DHT11 or DHT22 temperature and humidity sensor *(If not use a simple switch to input signal to the esp32)*
- Jumper wires  
- Breadboard  

### 💻 Software
- Arduino IDE  
- PubSubClient library (for MQTT)  
- WiFi and MQTT broker credentials  

---

## ⚙️ Setup Steps

### 1. 🛠️ Hardware Wiring

```
DHT11 Connections:
- VCC → 3.3V  
- GND → GND  
- DATA → GPIO 4 (you can change this in the code)
```

---

### 2. 💻 Arduino IDE Setup

1. Install the **ESP32 board support** in Arduino IDE.  *(Some times you may need the drivers for it. Download install and try to connect to esp32 again [[https://www.silabs.com/developer-tools/usb-to-uart-bridge-vcp-drivers]] . *
2. Install the following libraries:
   - `DHT sensor library` by Adafruit  
   - `Adafruit Unified Sensor`  
   - `PubSubClient`  

---

### 3. 🔌 MQTT Broker Setup

Use any of the following options:
- `test.mosquitto.org` (public)  
- Your own Mosquitto broker on your PC  
- HiveMQ broker or CloudMQTT  

---

## 🧠 Code

### 📜 `esp32_mqtt_dht.ino`

```cpp
#include <WiFi.h>
#include <PubSubClient.h>
#include "DHT.h"

#define DHTPIN 4
#define DHTTYPE DHT11

const char* ssid = "YOUR_WIFI_SSID";
const char* password = "YOUR_WIFI_PASSWORD";
const char* mqtt_server = "test.mosquitto.org";

WiFiClient espClient;
PubSubClient client(espClient);
DHT dht(DHTPIN, DHTTYPE);

void setup_wifi() {
  delay(10);
  WiFi.begin(ssid, password);
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
  }
}

void reconnect() {
  while (!client.connected()) {
    if (client.connect("ESP32Client")) {
	  //Here you can subscribe to any topic if needed
      //client.subscribe("test/topic");
      //
    } else {
      delay(5000);
    }
  }
}

void setup() {
  Serial.begin(115200);
  dht.begin();
  setup_wifi();
  client.setServer(mqtt_server, 1883);
}

void loop() {
  if (!client.connected()) {
    reconnect();
  }
  client.loop();

  float h = dht.readHumidity();
  float t = dht.readTemperature();

  if (!isnan(h) && !isnan(t)) {
    String payload = "Temp: " + String(t) + "°C, Humidity: " + String(h) + "%";
    client.publish("test/topic", payload.c_str());
  }

  delay(5000);
}
```

---

## ✅ Expected Output

- ESP32 connects to Wi-Fi.  
- Every 5 seconds, it publishes temperature and humidity to MQTT topic `test/topic`.  
- Use **MQTT Explorer** or **HiveMQ Web Client** to observe messages.  

---

## 🧪 Test and Verify

1. Open [HiveMQ Web Client](https://www.hivemq.com/demos/websocket-client/).  
2. Connect to broker: `broker.hivemq.com`, port `8000`, client ID: any.  
3. Subscribe to: `test/topic`.  
4. Watch the ESP32 send data!

---

## 📌 Notes

- ESP32 can also **subscribe** to topics and control devices (like LEDs) based on messages.  
- You can extend this lab by adding more sensors or subscribing to a topic to control an output.
## 🎯 Learning Outcomes

By completing this lab project, you will be able to:

- Understand the basics of the MQTT protocol and its role in IoT communication.
- Set up an ESP32 development board and connect it to a Wi-Fi network.
- Interface an environmental sensor (DHT11/DHT22) with the ESP32.
- Install and configure the Arduino IDE with necessary libraries for ESP32 and MQTT.
- Connect the ESP32 to a public or private MQTT broker.
- Publish sensor data (temperature and humidity) to an MQTT topic periodically.
- Use MQTT clients (like HiveMQ Web Client or MQTT Explorer) to subscribe and monitor messages.
- Gain foundational skills in IoT device communication, sensor data acquisition, and real-time messaging.
- Extend the project by subscribing to MQTT topics and controlling hardware outputs remotely.


>M.H.S. Gunathilaka 220199L