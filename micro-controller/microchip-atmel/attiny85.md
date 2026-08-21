# ATTiny85

## Parts
1. ATTiny85-20PU
2. Jumper Wires
3. Breadboard

## Arduino IDE Setup
1. File > Preferences > Additional boards manager URLs
2. Add JSON Lib URL
```
https://raw.githubusercontent.com/damellis/attiny/ide-1.6.x-boards-manager/package_damellis_attiny_index.json
```
3. Board Manager > Search "attiny" > attiny by David A. Mellis
4. Close and Reopen Arduino IDE

## Burn Bootloader via Arduino Uno/Duemilanove

## Upload Code

1. File > Examples > ArduinoISP > ArduinoISP Sketch
2. Upload ArduinoISP sketch to Uno

## Connect Arduino to ATtiny85

Arduino RST Pin > 10uF Electrolyte Capacitor > Arduino GND Pin

| SPI | ATtiny85 | Arduino Uno Q | Wire |
|:--:|:--:|:--:|:--:|
| - | VCC | 5V | Red |
| - | GND | GND | Black |
| MOSI | PB0 | Pin ~11 | Orange |
| MISO | PB1 | Pin 12 | Yellow |
| SCK | PB2 | Pin 13 | Green |
| SS | RST | Pin ~10 | Blue |

## Configure Arduino IDE for ATtiny85

1. Tools > Board > attiny > ATtiny25/45/85
2. Tools > Port > Select ATtiny Port
3. Tools > Clock > Internal 8 MHz
4. Tools > Processor > ATtiny85
5. Tools > Programmer > Arduino as ISP

## Change Clock Frequency

1. Find avrdude.exe and avrdude.config
2. change -pattiny85 with correct processor
3. -PCOMXX to the attiny comm port

Write CMDs below in Git Bash
1. Read Clock Frequency
```
"C:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\bin\avrdude.exe" "-CC:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\etc\avrdude.conf" -v -pattiny85 -cstk500v1 -PCOM11 -b19200 "-Ulfuse:r:-:h"
```
2. Change clock frequency to 1.6MHz
```
"C:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\bin\avrdude.exe" "-CC:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\etc\avrdude.conf" -v -pattiny85 -cstk500v1 -PCOM11 -b19200 "-Ulfuse:w:0xe3:m"
```
2. Change clock frequency to 8MHz
```
"C:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\bin\avrdude.exe" "-CC:\Users\{User}\AppData\Local\Arduino15\packages\arduino\tools\avrdude\8.0.0-arduino1\etc\avrdude.conf" -v -pattiny85 -cstk500v1 -PCOM11 -b19200 "-Ulfuse:w:0xe2:m"
```
