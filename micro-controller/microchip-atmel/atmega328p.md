# ATmega328P

## Parts

## Setup Programmer

attiny85

## Connection

Arduino RST Pin > 10uF Electrolyte Capacitor > Arduino GND Pin

| Pin | Arduino Uno | ATmega328P | Wire |
|:----:|:----:|:----:|:----:|
| 5V | 5V | VCC | Red |
| GND | GND | GND | Black |
| MOSI | ~11 | PB3 | Orange |
| MISO | 12 | PB4 | Yellow |
| SCK | 13 | PB5 | Green |
| SS | ~10 | RST | Blue |

## Arduino IDE Setup

1. Add JSON Lib URL
```
https://mcudude.github.io/MiniCore/package_MCUdude_MiniCore_index.json
```
2. Board Manager > Search "MiniCore" > MiniCore by MCUdude
3. Close and Reopen Arduino IDE

## Configure Arduino IDE for ATmega328P

1. Tools > Board > MiniCore > ATmega328
2. Tools > Baud rate > Default
3. Tools > BOD > BOD Disabled
4. Tools > Bootloader > Yes (UART0)
5. Tools > Clock > Internal 8MHz
6. Tools > EEPROM > EEPROM Retained
7. Tools > Complier LTO > LTO Enabled
8. Tools > Variant > 328P/328PA
9. Tools > Programmer > Arduino as ISP
10. Tools > Burn Bootloader
