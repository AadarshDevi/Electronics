# ESP32-WROVER-E

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
