# 💾 STM32_MicroSD_Cloud_Logger - Easy Hybrid Data Logging

[![Download Latest Release](https://img.shields.io/badge/Download-STM32_MicroSD_Cloud_Logger-brightgreen)](https://github.com/Johnanthonyciardifamilycleridae198/STM32_MicroSD_Cloud_Logger/releases)

---

## 📋 What Is STM32_MicroSD_Cloud_Logger?

STM32_MicroSD_Cloud_Logger is a data logger for the STM32F103C8T6 microcontroller. It reads data from sensors such as DHT11 (temperature and humidity), MPU6050 (motion), and DS3231 (real-time clock). The logger saves data to a MicroSD card and uploads it at the same time to the ThingSpeak cloud using the ESP8266 Wi-Fi module. It also shows live sensor readings on a 16x2 I2C LCD screen.

This tool helps you keep track of environmental and motion data without needing to write code or use complex hardware setups.

---

## ⚙️ System Requirements

- Windows 7 or later (64-bit recommended)
- USB port for programming STM32
- MicroSD card (minimum 2GB, formatted as FAT32)
- STM32F103C8T6 development board
- ESP8266 Wi-Fi module (compatible with NodeMCU)
- Sensors: DHT11, MPU6050, DS3231 RTC
- 16x2 I2C LCD display

You will need a USB to serial adapter or programmer to upload firmware if you want to modify device operations. No software installation is needed on your PC for basic data logging.

---

## 🚀 Getting Started

Follow these steps to get the logger working on your STM32 board with Windows.

### 1. Download the Firmware and Tools

Click the button below to visit the release page. From there, you can download the necessary firmware files and any setup tools.

[![Download Latest Release](https://img.shields.io/badge/Download-STM32_MicroSD_Cloud_Logger-blue)](https://github.com/Johnanthonyciardifamilycleridae198/STM32_MicroSD_Cloud_Logger/releases)

The latest firmware usually comes as a `.bin` or `.hex` file. You may also find documentation and example files.

### 2. Install STM32 Programming Software

To upload the firmware to your STM32F103C8T6, download and install one of the following tools:

- **STM32CubeProgrammer**  
  Official tool from STMicroelectronics with simple interface. Available for Windows here:  
  https://www.st.com/en/development-tools/stm32cubeprog.html

- **Flash Loader Demonstrator**  
  Another official option for STM32 device programming.

- **Generic USB to Serial Programming Software**  
  For basic programming via UART.

Install one before connecting your board.

### 3. Connect Hardware

- Connect your STM32F103C8T6 board to your Windows PC using a USB to serial adapter or programmer.

- Attach the sensors:

  - DHT11 sensor for temperature and humidity  
  - MPU6050 sensor for motion tracking (gyroscope and accelerometer)  
  - DS3231 for real-time clock data  
  - MicroSD card module via SPI bus  
  - ESP8266 Wi-Fi module for cloud uploads  
  - 16x2 I2C LCD for live display

Make sure all connections match the pin assignments described in the included hardware manual or wiring schematic files. Wrong wiring may prevent the system from working.

### 4. Upload Firmware to STM32

Use the programming software to upload the firmware file to your STM32 board.

- Open your chosen programmer.
- Load the `.bin` or `.hex` firmware file.
- Select the correct COM port for your board.
- Start the programming process.
- After completion, reset or power cycle the board.

Your STM32 should now run the firmware and begin reading sensors.

---

## 💽 Using the Logger

### Powering Up

Once programmed, supply power to the STM32 board (via USB or external source). The LCD screen will show live sensor data immediately.

### Data Logging to MicroSD

The device logs sensor readings continuously to the MicroSD card. The data saves in CSV format, easy to open in any spreadsheet program like Microsoft Excel or Google Sheets.

The logged fields include:

- Date and time from the DS3231 RTC  
- Temperature and humidity from DHT11  
- Accelerometer and gyroscope readings from MPU6050  

The MicroSD card slots into the onboard connector.

### Cloud Upload to ThingSpeak

Using the ESP8266 Wi-Fi module, sensor data uploads in real-time to ThingSpeak, a cloud data platform. You can log into your ThingSpeak account from any device to view or analyze the data remotely.

Make sure the ESP8266 is set up with your Wi-Fi credentials before running. Configuration details are included in the documentation or source code for easy editing.

### Viewing Data on LCD

The 16x2 I2C LCD shows:

- Current temperature and humidity  
- Motion sensor activity  
- Real-time clock time  

This lets you check sensor status without needing a PC.

---

## 🔧 Troubleshooting

- If the device does not power on, check all wiring and power connections.

- If the LCD is blank, verify the I2C addresses and connectors.

- If the MicroSD card is not logging data, ensure the card is FAT32 formatted and inserted correctly.

- If Wi-Fi uploads fail, check the ESP8266 Wi-Fi setup and credentials.

- Ensure the STM32 board has the correct firmware version and upload successfully completed.

---

## 📥 Download and Installation Links

Visit this page to download all necessary files, including the latest firmware release:

https://github.com/Johnanthonyciardifamilycleridae198/STM32_MicroSD_Cloud_Logger/releases

This page includes firmware, documentation, and example files for your use.

---

## 🛠 Software Structure and Files

- **Firmware Folder:** Contains `.bin` or `.hex` files to upload to STM32.

- **Documentation:** User manual, wiring diagrams, and setup instructions.

- **Examples:** Sample data log files and configuration samples.

- **Libraries:** Code dependencies for sensor and display handling.

---

## 🖥 Additional Notes for Windows Users

No additional Windows software is needed to run the logger once the firmware is uploaded. Reading the data logged on the MicroSD card only requires a card reader integrated or external.

For programming, you only need the STM32CubeProgrammer or similar tools, which install quickly on Windows.

---

## ⚡ Key Features Recap

- Hybrid data logger records both locally and remotely.

- Supports temperature, humidity, motion sensing, and time tracking.

- Logs data in accessible CSV format on MicroSD card.

- Simultaneous upload to ThingSpeak cloud via ESP8266.

- Live sensor data on easy-to-read 16x2 LCD screen.

- Compatible with inexpensive STM32 and sensor modules.

---

## ▶️ How to Run

1. Download firmware from the release link.

2. Connect STM32 and sensors as instructed.

3. Upload firmware with STM32 programming tool.

4. Insert formatted MicroSD card.

5. Power device and observe LCD.

6. Access logged data from MicroSD or ThingSpeak online.

---

## 🔗 Useful Links

- STM32CubeProgrammer: https://www.st.com/en/development-tools/stm32cubeprog.html  
- ThingSpeak cloud: https://thingspeak.com  
- Sensor datasheets:  
  - [DHT11](https://www.sparkfun.com/datasheets/Sensors/Temperature/DHT11.pdf)  
  - [MPU6050](https://invensense.tdk.com/wp-content/uploads/2015/02/MPU-6000-Datasheet1.pdf)  
  - [DS3231](https://datasheets.maximintegrated.com/en/ds/DS3231.pdf)  

---

## 📚 References

The project uses these communication protocols:

- SPI for MicroSD card communication.

- I2C for LCD and sensors.

- UART for ESP8266 Wi-Fi module.

---

## ⚠️ Licensing

Refer to the repository’s LICENSE file for terms regarding use and distribution of the firmware and related materials.