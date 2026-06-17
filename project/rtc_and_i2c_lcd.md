# DS1307 RTC Module and I2C LCD 16x2

## Components
1. I2C LCD 16x2
2. Elegoo DS1307 Module V03
3. ESP32-WROOM-32UE
4. Jumper Wires

## Connection(s)

| I2C LCD | ESP32 | Wire Color |
|:-------:|:--------:|:-------:|
| SDA | GPIO 21 (I2C SDA) | Orange |
| SCL | GPIO 22 (I2C SCL) | Yellow |
| VCC | 5V | Green |
| GND | GND | White |

| DS1307 | ESP32 | Wire Color |
|:-------:|:--------:|:-------:|
| SDA | GPIO 21 (I2C SDA) | Orange |
| SCL | GPIO 22 (I2C SCL) | Yellow |
| VCC | 5V | Green |
| GND | GND | White |

## Library Manager
1. LiquidCrystal_I2C by Martin Kubovcik, Frank de Brabander
2. RTClib by Adafruit (Install _**with**_ dependencies)

## Programming
1. Create Objects

## Sources / Resources
1. [LiquidCrystal I2C Library](https://github.com/markub3327/LiquidCrystal_I2C/tree/master)
2. [ESP32: Guide for DS1307 RTC](https://randomnerdtutorials.com/esp32-ds1307-real-time-clock-rtc-arduino/)
3. [ESP32 - DS1307 RTC Module](https://esp32io.com/tutorials/esp32-ds1307-rtc-module)
