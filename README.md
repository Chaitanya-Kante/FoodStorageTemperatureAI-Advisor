# FoodStorageTemperatureAI-Advisor
Arduino + Python system for DHT11 temperature sensing, food detection, and TTS advice.
This repository contains two main components:

1. **Arduino Sketch** – Reads ambient temperature and humidity from a DHT11 sensor and sends readings over serial.  
2. **Python Script** – Captures an image via webcam, reads temperature from Arduino, uses OpenAI to detect food type, and provides voice feedback on whether the temperature is ideal for that food.

---

## 📌 Features

- **Real-time Temperature Sensing**  
  - Uses DHT11 to measure ambient temperature (°C).  
- **Computer Vision & Food Recognition**  
  - Captures and resizes webcam images.  
  - Encodes images to Base64 and queries OpenAI’s vision model to detect food.  
- **AI-Driven Storage Advice**  
  - Asks OpenAI whether the measured temperature is ideal for the detected food and requests shelf-life information.  
- **Voice Feedback**  
  - Reads out results (detected food, ideal-temperature advice, shelf life) via TTS using `edge_tts`.

---

## 🔧 Hardware Requirements

- **Arduino Uno** (or compatible board)  
- **DHT11 Temperature & Humidity Sensor**  
- 10 kΩ resistor (pull-up)  
- Female–male jumper wires  
- USB A–B cable  
- Breadboard (optional)

### Wiring

| DHT11 Pin | Arduino Pin | Notes                            |
| :-------: | :---------: | :------------------------------: |
| VCC       | 5 V         | Power                            |
| GND       | GND         | Ground                           |
| DATA      | D2          | Digital I/O (with 10 kΩ pull-up) |

1. Mount DHT11 on breadboard.  
2. Wire VCC → 5 V, GND → GND.  
3. DATA → D2, and add 10 kΩ resistor between DATA and VCC.

---

## 🛠 Software Requirements

### Arduino IDE
- **Version**: 1.8.x or later  

### Python
- **Version**: 3.8+  
- **Dependencies** (install via `pip` or `pip3`):

  ```bash
  pip install opencv-python pyserial openai edge_tts
