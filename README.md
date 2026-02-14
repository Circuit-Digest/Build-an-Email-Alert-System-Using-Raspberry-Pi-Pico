
## 🚀 Build an Email Alert System Using Raspberry Pi Pico W

This project demonstrates how to build an Email Alert System using Raspberry Pi Pico W and an IR sensor.  
When an object is detected, the Pico W connects to WiFi and sends an automatic email notification using the CircuitDigest Cloud Email Notification API.

This system is ideal for real-time monitoring, intrusion detection, and IoT-based alert applications.

---

## 🧠 Project Overview

The Raspberry Pi Pico W continuously monitors an IR sensor connected to GPIO 2.

When:
- An object is detected
- Detection remains valid for a defined duration

The system:
- Connects to WiFi
- Generates a secure HTTPS request
- Sends structured JSON data to Cloud Email API
- Triggers an email alert instantly

This creates a reliable Pico W email notification system.

---

## 🛠️ Components Required

| Component | Quantity |
|------------|----------|
| Raspberry Pi Pico W | 1 |
| IR Sensor Module | 1 |
| Breadboard | 1 |
| Connecting Wires | As required |

---

## 🔌 Circuit Connections

| IR Sensor Pin | Pico W Connection |
|--------------|-------------------|
| VCC | 3.3V |
| GND | GND |
| OUT | GPIO 2 |

GPIO 2 is configured as a digital input to monitor object detection.

---

## ⚙️ Working Principle

1. Pico W initializes WiFi connection.
2. IR sensor monitors object presence.
3. If object is detected:
   - Detection timer starts.
4. If detection remains valid:
   - Email alert is triggered.
5. Boolean flag prevents repeated emails.
6. When object leaves:
   - System resets and continues monitoring.

---

## 🌐 Pico W Email Notification Process

- WiFi connection established
- Secure HTTPS client created
- JSON payload constructed
- Email template selected
- Cloud API processes request
- Email delivered to registered address

---

## 🔐 Key Features

✔ Real-time motion detection  
✔ Secure HTTPS communication  
✔ Cloud-based Email Notification API  
✔ Event-based alert system  
✔ Prevents duplicate alerts  
✔ Minimal hardware requirement  

---

## 📄 Important Code Sections

### Include Required Libraries
```cpp
#include <WiFi.h>
#include <WiFiClientSecure.h>
#define IR_SENSOR_PIN 2
```

### WiFi & API Configuration
```cpp
const char* ssid = "Your wifi name";
const char* password = "your password";
const char* host = "www.circuitdigest.cloud";
const int port = 443;
```

### Email Trigger Logic
```cpp
if (currentDetection && detectionDuration >= DETECTION_DURATION && !emailSent) {
  sendEmail(totalDetections);
  emailSent = true;
}
```

---

## 📬 Applications

- Intrusion Detection System  
- Home Security Monitoring  
- Warehouse Monitoring  
- Restricted Area Surveillance  
- Smart Automation Systems  
- Remote Monitoring Solutions  

---

## 🔧 Troubleshooting

### Email Not Received
- Check API key and template ID
- Verify registered email
- Check spam folder
- Ensure internet connection is stable

### WiFi Not Connecting
- Verify SSID and password
- Ensure 2.4GHz network
- Check signal strength

### False Detection
- Avoid direct sunlight
- Adjust IR sensor sensitivity
- Increase detection duration in code

### Multiple Email Alerts
- Ensure emailSent flag is properly implemented
- Increase detection delay time

---

## 🔮 Future Enhancements

- Add PIR or ultrasonic sensor support
- Add image-based email alerts
- Cloud dashboard integration
- SMS and mobile push notification support
- Data logging and analytics

---

## 📚 Learning Outcomes

After completing this project, you will understand:

- Raspberry Pi Pico W WiFi connectivity
- Secure HTTPS communication
- JSON payload formatting
- Cloud API integration
- Event-based IoT alert systems

---

## 📌 Conclusion

This project successfully demonstrates how to build an Email Alert System using Raspberry Pi Pico W with minimal hardware. By integrating sensor detection with secure cloud communication, the system delivers reliable real-time notifications.

It is simple, scalable, and suitable for both learning and real-world monitoring applications.

---
Author :

Vedhathiri
