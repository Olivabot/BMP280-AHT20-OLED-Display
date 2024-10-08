# BMP280 + AHT20 + OLED Display (Arduino Project)

This Arduino project reads temperature, humidity, and pressure from the AHT20 and BMP280 sensors and displays the values on an OLED screen (SSD1306). The code also prints the data to the Serial Monitor for debugging purposes.
![photo_2024-10-08_15-04-46](https://github.com/user-attachments/assets/7ea75ab0-1bb3-4fc4-bd34-694010e7ae16)

## Features
- Reads **temperature** and **humidity** from the AHT20 sensor.
- Reads **temperature** and **pressure** from the BMP280 sensor.
- Displays the readings on a **128x64 OLED display** using the SSD1306 driver.
- Displays pressure both in **hPa** and in **atmospheres (atm)**.
- Data is printed to the **Serial Monitor** for debugging.

## Hardware Requirements
- **Arduino** (e.g., ESP32, Arduino Uno, etc.)
- **BMP280** (Pressure and Temperature sensor)
- **AHT20** (Temperature and Humidity sensor)
- **OLED 128x64 display** (SSD1306 driver)
- Jumper wires for connections

## Connections
### AHT20 Sensor:
- **VCC** to 3.3V or 5V (depending on your sensor)
- **GND** to GND
- **SDA** to Arduino's SDA (A4 on most boards, or GPIO 21 on ESP32)
- **SCL** to Arduino's SCL (A5 on most boards, or GPIO 22 on ESP32)

### BMP280 Sensor:
- **VCC** to 3.3V or 5V
- **GND** to GND
- **SDA** to Arduino's SDA
- **SCL** to Arduino's SCL

### OLED Display:
- **VCC** to 3.3V or 5V
- **GND** to GND
- **SDA** to Arduino's SDA
- **SCL** to Arduino's SCL

## Software Requirements
- Arduino IDE (1.8.13 or higher)
- Libraries (install via Arduino Library Manager):
  - `Adafruit SSD1306` for the OLED display
  - `Adafruit GFX` (required for SSD1306)
  - `Adafruit BMP280` for the BMP280 sensor
  - `Adafruit AHTX0` for the AHT20 sensor

## Installation
1. Clone or download the repository to your local machine.
2. Open the `.ino` file in the Arduino IDE.
3. Install the necessary libraries via **Sketch > Include Library > Manage Libraries**.
4. Connect your Arduino and upload the code.

## Usage
Once the code is uploaded:
1. Open the Serial Monitor (set baud rate to **115200**) to see temperature, humidity, and pressure readings printed every 2 seconds.
2. The OLED screen will also display:
   - Humidity (from AHT20)
   - Temperature (from both AHT20 and BMP280)
   - Pressure in hPa and atm (from BMP280)

## Example Output on Serial Monitor:
```
Temp (AHT20): 24.56 C
Humidity: 50.23 %
Temp (BMP280): 23.95 C
Pressure: 0.993 atm
Pressure: 1007.23 hPa
```

## Troubleshooting
- **No display on the OLED**: Ensure the correct I2C address is set for the OLED (`0x3C`) and that all connections are secure.
- **Sensor not found**: Double-check the wiring and I2C addresses for the BMP280 (`0x76` or `0x77`) and AHT20 (`0x38`).
- **Serial Monitor shows gibberish**: Ensure the baud rate in the Serial Monitor is set to `115200`.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
