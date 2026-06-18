# I2C LCD 16x2

## Components
1. I2C LCD 16x2
2. ESP32-WROVER-E
3. Jumper Wires

## Connection(s)

| I2C LCD | ESP32 | Wire Color |
|:-------:|:--------:|:-------:|
| SDA | GPIO 21 (I2C SDA) | Orange |
| SCL | GPIO 22 (I2C SCL) | Yellow |
| VCC | 5V | Green |
| GND | GND | White |

## Library Manager
1. LiquidCrystal_I2C by Martin Kubovcik, Frank de Brabander

## Programming
1. Import library
```c
#include <LiquidCrystal_I2C.h>
```

2. Create LCD object
```c
LiquidCrystal_I2C lcd(0x27, 16, 2);
```
The LCD has 20 cols and 4 rows. **_The address for the I2C LCD is 0x27._**

3. initialize lcd
```c
lcd.init(); // create obj
lcd.backlight(); // turn backlight on
```

4. Set cursor
```c
lcd.setCursor(0, 0); // col, row
```

5. Print "Hello LCD World!"
```c
lcd.print("Hello LCD World!");
```

## Projects
1. [I2C LCD 16x2 and HW504 Joystick Module](https://github.com/AadarshDevi/Electronics/blob/master/project/i2c-lcd-16x2-hw504.md)

## Sources / Resources
1. Nasa Internship
