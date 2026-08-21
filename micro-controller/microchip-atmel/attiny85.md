# ATTiny85

## Parts
1. ATTiny85-20PU
2. Jumper Wires
3. Breadboard

## Setup

### Arduino Uno Q
1. Upload Arduino ISP: File > Examples > ArduinoISP > ArduinoISP
2. Tools > Board > Arduino Uno Q

### Arduino IDE

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
9. Tools > Programmer > Arduino as ISP

## Connection

## Arduino Duemilanove
Arduino Duemilanove - RST > 10uF Capacitor > Arduino Duemilanove - GND
| SPI | ATtiny85 | Arduino Uno Q | Wire |
|:--:|:--:|:--:|:--:|
| - | VCC | 5V | Red |
| - | GND | GND | Black |
| MOSI | PB0 | Pin ~11 | Orange |
| MISO | PB1 | Pin 12 | Yellow |
| SCK | PB2 | Pin 13 | Green |
| SS | RST | Pin ~10 | Blue |

## Upload Code

Sketch > Upload using Programmer

## Additional

### Change Clock Frequency

Things to Change:
1. Find avrdude.exe and avrdude.config
2. change -pattiny85 with correct processor
3. -PCOMXX to the attiny comm port

Commands (Git Bash):
1. Read Clock Frequency
```
"C:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\bin\avrdude.exe" "-CC:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\etc\avrdude.conf" -v -pattiny85 -cstk500v1 -PCOM11 -b19200 "-Ulfuse:r:-:h"
```
2. Clock to 6.4MHz
```
"C:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\bin\avrdude.exe" "-CC:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\etc\avrdude.conf" -v -pattiny85 -cstk500v1 -PCOM11 -b19200 "-Ulfuse:w:0xe3:m"
```
2. Clock to 8MHz
```
"C:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\bin\avrdude.exe" "-CC:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\etc\avrdude.conf" -v -pattiny85 -cstk500v1 -PCOM11 -b19200 "-Ulfuse:w:0xe2:m"
```
