# Troubleshooting

## Common Problems

### Device Won't Connect to WiFi

**Symptoms**: LCD shows "WiFi: Disconnected", no data in MQTT

**Solutions**:
- Double-check WiFi credentials in code
- Make sure you're using 2.4GHz WiFi (ESP32 doesn't support 5GHz)
- Try moving closer to your router
- Check if your network requires special login (like captive portal)

### LCD Display Not Working  

**Symptoms**: Backlight on but no text, or completely dark

**Solutions**:
- Check I2C connections (SDA to GPIO 21, SCL to GPIO 22)
- Try different I2C address in code (0x27 or 0x3F)
- Verify power connections (3.3V and GND)
- Test with I2C scanner code

### DHT22 Sensor Not Reading

**Symptoms**: Temperature shows as 0 or NaN, humidity readings invalid

**Solutions**:
- Verify the 10kΩ pull-up resistor between VCC and Data pins
- Check data pin connection to GPIO 4
- Make sure you have a genuine DHT22 (not DHT11)
- Try replacing the sensor

### No MQTT Data

**Symptoms**: Device connects to WiFi but no data in MQTT broker

**Solutions**:
- Check MQTT broker address and port
- Verify internet connectivity
- Try a different MQTT broker
- Check firewall settings

### Button Not Working

**Symptoms**: Pressing button doesn't trigger alarm

**Solutions**:
- Check button wiring (one side to GPIO 2, other to GND)
- Verify button is not stuck or broken
- Check for loose connections

### LED Not Lighting

**Symptoms**: Status LED never turns on

**Solutions**:
- Check LED polarity (long leg should connect to GPIO 5 through resistor)
- Verify 220Ω resistor is in series with LED
- Try a different LED
- Test GPIO 5 with multimeter

## Getting Help

### Serial Monitor Debug

Always check the Serial Monitor (115200 baud) for debug messages:
- ESP32 IoT Device Starting...
- WiFi: Connecting to MyNetwork...
- WiFi: Connected! IP: 192.168.1.100
- MQTT: Connecting to broker...
- MQTT: Connected!
- DHT22: Temperature: 25.6°C, Humidity: 65.2%

### Useful Debug Commands

Add these to your code for debugging:

```cpp
// Print WiFi status
Serial.print("WiFi Status: ");
Serial.println(WiFi.status());

// Print free memory
Serial.print("Free heap: ");
Serial.println(ESP.getFreeHeap());

// Print MQTT connection state
Serial.print("MQTT State: ");
Serial.println(client.state());
