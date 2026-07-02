# Freenove ESP32-WROVER-CAM

## Pinout

<img width="1284" height="855" alt="image" src="https://github.com/user-attachments/assets/79b1fa50-6972-4e9b-a1ee-8ff55a6b94f4" />

## Setup

### Install Driver
1. Download and install [CH340 Driver](https://search.wch-ic.com/) from Nanjing Qinheng Microelectronics Co., Ltd.
  - Windows: CH341SER.EXE
  - MacOS: CH341SER_MAC.ZIP
  - Linux: CH341SER_LINUX.ZIP
2. [Win11] Plugin board and open Device Manager
3. Ports (COM & LPT) > **USB-SERIAL CH340** will be there

### Board Manager
1. File > Preferences > Additional boards mamanger URLs window button
2. Add json link
```json
   https://espressif.github.io/arduino-esp32/package_esp32_index.json
```
3. Close & reopen Arduino IDE
4. Install: esp32 by Espressif Systems

### Tools
1. Tools > Board > esp32 > ESP32 Wrover Module

## Upload Code
1. Choose program to upload
2. Click upload button

## Additional Info

### Small Defective
When binking the onboard programmable led, HIGH turns the led off and LOW turns it on. This is because the led is connected to 3V3 (I believe) and not GND.
