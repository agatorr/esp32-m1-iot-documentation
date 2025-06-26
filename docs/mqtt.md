# MQTT Communication Guide

## What is MQTT?

MQTT is a lightweight messaging protocol perfect for IoT devices. Your ESP32 uses it to send sensor data to the cloud.

## MQTT Topics Used

Your device publishes data to these topics:
## Message Examples

```json
Environmental Data
{
  "temperature": 25.6,
  "humidity": 65.2,
  "timestamp": "2024-06-25T14:30:00Z"
}

System Health
{
  "uptime": 3600,
  "free_heap": 245760,
  "wifi_rssi": -45
}

Alarm Event
{
  "alarm_type": "manual",
  "severity": "high",
  "message": "Manual alarm triggered"
}
