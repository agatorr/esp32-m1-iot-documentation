# Getting Started

## What You Need

- ESP32 development board
- DHT22 temperature/humidity sensor
- 16x2 LCD display (I2C)
- Push button
- LED
- Resistors (220Ω, 10kΩ)
- Breadboard and wires

## Software Setup

1. **Install Arduino IDE**
2. **Add ESP32 board support**
3. **Install required libraries:**
   - DHT sensor library
   - LiquidCrystal I2C
   - PubSubClient (for MQTT)

## Basic Configuration

```cpp
// WiFi credentials
const char* ssid = "YOUR_WIFI_NAME";
const char* password = "YOUR_WIFI_PASSWORD";

// MQTT settings
const char* mqtt_server = "broker.hivemq.com";
const int mqtt_port = 1883;
