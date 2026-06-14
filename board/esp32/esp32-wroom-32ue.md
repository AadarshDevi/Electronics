# ESP32-WROOM-32UE

## Setup

### Install Driver
1. Download and install [CP210x Driver](https://www.silabs.com/software-and-tools/usb-to-uart-bridge-vcp-drivers?tab=downloads) from Silicon Labs
2. [Win11] Plugin board and open Device Manager
3. Ports (COM & LPT) > **Silicon Labs CP210x USB to UART Bridge** will be there

### Board Manager
1. File > Preferences > Additional boards mamanger URLs window button
2. Add json link
```json
   https://espressif.github.io/arduino-esp32/package_esp32_index.json
```
3. Close & reopen Arduino IDE
4. Install: esp32 by Espressif Systems

### Tools
1. Tools > Board > esp32 > ESP32-WROOM-DA Module
2. Tools > Flash Mode > DIO

## Upload Code
1. Choose program to upload
2. Click upload button
3. When `Connecting..........` appears, press & hold the boot button
4. Once `Hard resetting via RTS pin...` is in the terminal, press the EN button

## Additional Info

1. Board does not have an onboard programmable led

### Diagnostic / Board Info
```
ets Jul 29 2019 12:21:46

rst:0x1 (POWERON_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:1
load:0x3fff0030,len:4876
ho 0 tail 12 room 4
load:0x40078000,len:16560
load:0x40080400,len:3500
entry 0x400805b4
```
The ESP32 will send out diagnostic/board information like above. In order to not get this information on the Serial Monitor/Communication, GPIO15 (15, IO15) has to be connected to GND.

[ WARNING ] When GPIO15 is connected to GND, code cannot be uploaded.
