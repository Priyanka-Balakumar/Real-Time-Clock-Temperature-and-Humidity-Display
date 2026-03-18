# Arduino Air Quality & Environment Monitor

An IoT-based monitoring system designed to track indoor air safety and comfort levels.This project utilizes an analog gas sensor and a DHT11 sensor to provide instant feedback on air purity, temperature, and humidity.

## Features

  **Real-time Air Quality Analysis:** Categorizes air quality from "Good" to "Toxic" based on gas concentration levels.
  **Climate Tracking:** Measures temperature in Celsius and Relative Humidity (RH) percentage.
  **OLED Visualization:** Displays data on a 128x64 SSD1306 OLED screen using custom fonts for better readability.
  **Serial Debugging:** Includes error handling for sensor failures via the Serial Monitor.

##  Hardware Requirements

  **Microcontroller:** Arduino (Uno, Nano, or Mega)
  **Display:** SSD1306 OLED (128x64)
  **Sensors:**
      MQ-series Gas Sensor (Analog output connected to `A0`)
      DHT11 Temperature & Humidity Sensor 
  * **Connecting Wires & Breadboard**

##  Pin Mapping

| Component | Arduino Pin | Description |

| **Gas Sensor** | `A0` |Analog input for gas concentration|
| **DHT11** | `D2` |Digital data pin|
| **OLED SDA** | `A4` (SDA) |I2C Data (standard for Uno) |
| **OLED SCL** | `A5` (SCL) |I2C Clock (standard for Uno) |

##  Air Quality Thresholds

The system evaluates the `gasLevel` (analog reading) using the following logic:

**\< 181:** Good\!
**181 - 224:** Poor\!
**225 - 299:** Very bad\!
**300 - 349:** ur dead\! (High Danger)
**\> 350:** Toxic

##  Installation & Setup

1.  **Install Libraries:** Ensure you have the following libraries installed in your Arduino IDE:
      `Adafruit_GFX` 
      `Adafruit_SSD1306`
      `DHT sensor library`
2.  **Wiring:** Connect the components according to the [Pin Mapping](https://www.google.com/search?q=%23-pin-mapping) section.
3.  **Upload:** Open `airquality.ino` in the Arduino IDE and upload it to your board.
4.  **Monitor:** Open the Serial Monitor at **9600 baud** to check for initialization status.
