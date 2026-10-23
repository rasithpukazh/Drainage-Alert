# Smart Drain Monitoring System 🚧

## 📌 Project Overview
The **Smart Drain Monitoring System** is an IoT-based project designed to monitor drainage water levels and detect potential blockage conditions. It uses an ESP32 microcontroller and an ultrasonic sensor to measure the distance between the sensor and the water surface. When the measured distance crosses a predefined threshold, the system activates an alert using a buzzer and LED, while displaying the status on an OLED screen.

The system aims to support early identification of possible drainage issues and help improve drainage maintenance.

## 🎯 Objectives
- Monitor drainage water levels using an ultrasonic sensor.
- Identify potential blockage conditions based on a configurable threshold.
- Provide alerts using a buzzer and LED.
- Display sensor readings and system status on an OLED display.
- Explore future IoT-based remote monitoring for municipal authorities.

## 🛠️ Components Required
- ESP32 Development Board
- HC-SR04 Ultrasonic Sensor
- 0.96-inch SSD1306 OLED Display
- Buzzer
- Red LED
- 220Ω resistor
- Two 1kΩ resistors for the ultrasonic sensor's ECHO voltage divider
- Jumper wires
- Suitable battery and regulated power supply

## ⚙️ Working Principle
1. The ultrasonic sensor measures the distance to the water surface.
2. The ESP32 reads and processes the sensor data.
3. The measured distance is compared with a predefined threshold.
4. If the reading indicates a possible high water level, the buzzer and LED provide an alert.
5. The OLED displays the distance and current system status.

**Note:** This prototype uses a threshold-based indication. A high water level or short sensor distance alone does not confirm that a drain is blocked.

## 🔌 Hardware Connections

| Component | ESP32 Connection |
|---|---|
| HC-SR04 TRIG | GPIO 5 |
| HC-SR04 ECHO | GPIO 18 through a voltage divider |
| HC-SR04 VCC | Regulated 5V |
| OLED SDA | GPIO 21 |
| OLED SCL | GPIO 22 |
| OLED VCC | 3.3V |
| Buzzer (+) | GPIO 19, subject to current requirements |
| LED (+) | GPIO 23 through a 220Ω resistor |
| All GND pins | Common GND |

**Safety:** The ESP32 GPIO pins are not 5V tolerant. Never connect the HC-SR04 ECHO pin directly to an ESP32 GPIO. Use a suitable voltage divider.

## 💻 Software Requirements
- Arduino IDE
- ESP32 board package by Espressif Systems
- Adafruit GFX Library
- Adafruit SSD1306 Library
- Adafruit BusIO Library

## 🚀 How to Run
1. Install the Arduino IDE.
2. Install the ESP32 board package and required libraries.
3. Open `esp32/smart_drain_monitor.ino`.
4. Select the appropriate ESP32 board and COM port.
5. Upload the code using USB.
6. Connect the hardware according to the wiring table.
7. Power the prototype using a suitable regulated supply.
8. Observe the distance and status on the OLED display and check the buzzer/LED alerts.

## 🌐 Web Dashboard
The `web/index.html` file contains a **dashboard demonstration** for presenting the project concept. Its current alert and safe-status controls use simulated data. It is not yet connected to live ESP32 sensor readings.

Future
