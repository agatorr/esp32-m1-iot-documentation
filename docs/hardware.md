
```markdown
# Hardware Setup

## Wiring Diagram

Connect your components as follows:

| Component | ESP32 Pin | Notes |
|-----------|-----------|-------|
| DHT22 Data | GPIO 4 | Add 10kΩ pull-up resistor |
| DHT22 VCC | 3.3V | Power |
| DHT22 GND | GND | Ground |
| LCD SDA | GPIO 21 | I2C Data |
| LCD SCL | GPIO 22 | I2C Clock |
| LCD VCC | 3.3V | Power |
| LCD GND | GND | Ground |
| Button | GPIO 2 | Uses internal pull-up |
| LED + | GPIO 5 | Through 220Ω resistor |
| LED - | GND | Ground |

## Step-by-Step Assembly

### 1. Connect the DHT22 Sensor
- VCC → ESP32 3.3V
- Data → ESP32 GPIO 4 (with 10kΩ resistor to 3.3V)
- GND → ESP32 GND

### 2. Connect the LCD Display
- VCC → ESP32 3.3V
- GND → ESP32 GND  
- SDA → ESP32 GPIO 21
- SCL → ESP32 GPIO 22

### 3. Connect the LED
- Long leg → 220Ω resistor → ESP32 GPIO 5
- Short leg → ESP32 GND

### 4. Connect the Button
- One side → ESP32 GPIO 2
- Other side → ESP32 GND

## Testing

1. Power on the ESP32
2. LCD should light up
3. Check Serial Monitor for sensor readings
4. Press button to test alarm

## Common Issues

- **LCD not working**: Check I2C address (usually 0x27 or 0x3F)
- **DHT22 no data**: Verify pull-up resistor connection
- **LED not lighting**: Check polarity and resistor
