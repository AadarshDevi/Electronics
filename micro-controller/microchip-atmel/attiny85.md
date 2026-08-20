# ATTiny85

## Setup
1. Add JSON Lib
```
https://raw.githubusercontent.com/damellis/attiny/ide-1.6.x-boards-manager/package_damellis_attiny_index.json
```
2. Install Board Library: Board Manager > Search "attiny" by David A. Mellis
3. Completely Close Arduino IDE
4. Open Arduino IDE
5. Tools > Board > attiny > ATtiny25/45/85
6. Tools > Port > Select ATtiny Port
7. Tools > Clock > Internal 8 MHz
8. Tools > Processor > ATtiny85

## Parts
1. ATTiny85-20PU
2. Jumper Wires
3. Breadboard

## Connection

Arduino Uno Q :: 3V3 > 10uF Capacitor > Arduino Uno Q :: GND

| SPI | ATtiny85 | Arduino Uno Q | Wire |
|:--:|:--:|:--:|
| - | VCC | 5V | Red |
| - | GND | GND | Black |
| MOSI | PB0 | Pin ~11 | Orange |
| MISO | PB1 | Pin 12 | Yellow |
| SCK | PB2 | Pin 13 | Green |
| SS | RST | Pin ~10 | Blue |

## Upload Code

Upload Code
