# I2C LCD 16x2 and HW504 Joystick Module

## Aim
Display the joystick values on an LCD.

## Components
1. [ESP32-WROVER-E](https://github.com/AadarshDevi/Electronics/blob/master/board/esp32/esp32-wrover-e.md)
2. [I2C LCD 16X2](https://github.com/AadarshDevi/Electronics/blob/master/display/lcd/lcd-16x2-i2c.md?plain=1)
3. [HW504 Joystick Module](https://github.com/AadarshDevi/Electronics/blob/master/joystick/hw504.md?plain=1)
4. Jumper Cables
5. Breadboard

## Connection(s)
| I2C LCD | ESP32 | Wire Color |
|:-------:|:--------:|:-------:|
| SDA | GPIO 21 (I2C SDA) | Orange |
| SCL | GPIO 22 (I2C SCL) | Yellow |
| VCC | 5V | Green |
| GND | GND | White |

| HW504 | ESP32 | Wire Color |
|:-------:|:--------:|:-------:|
| VRx (X Axis) | GPIO 14 | Orange |
| VRy (Y Axis) | GPIO 12 | Yellow |
| VCC | 3V3 | Green |
| GND | GND | White |

## Library Manager
1. LiquidCrystal_I2C by Martin Kubovcik, Frank de Brabander

## Programming
Code written for the project
