# Elegoo DS1307 Module V03

## Components
1. Elegoo DS1307 Module V03
2. ESP32-WROOM-32UE
3. Jumper Wires

## Connection(s)
| DS1307 | ESP32 | Wire Color |
|:-------:|:--------:|:-------:|
| SDA | GPIO 21 (I2C SDA) | Orange |
| SCL | GPIO 22 (I2C SCL) | Yellow |
| VCC | 5V | Green |
| GND | GND | White |

## Library Manager
1. RTClib by Adafruit (Install _**with**_ dependencies)

## Programming
1. Create obj
```c
#include <RTClib.h>
RTC_DS1307 rtc;
```

2. Initiate obj
```c
if (! rtc.begin()) {
  Serial.println("RTC module is NOT found");
  while (1);
}
```

3. Set date and time
```c
rtc.adjust(DateTime(F(__DATE__), F(__TIME__)));
```

4. get date & time
```c
DateTime now = rtc.now();
```

5. get info from DS1307
```c
Serial.println(now.month());
Serial.println(now.day());
Serial.println(now.year());
Serial.println(now.hour());
Serial.println(now.minute());
Serial.println(now.second());
```

## Projects
1. [DS1307 RTC Module & I2C LCD 16x2](https://github.com/AadarshDevi/Electronics/tree/master/project)

## Sources / Resources
1. [ESP32: Guide for DS1307 RTC](https://randomnerdtutorials.com/esp32-ds1307-real-time-clock-rtc-arduino/)
2. [ESP32 - DS1307 RTC Module](https://esp32io.com/tutorials/esp32-ds1307-rtc-module)
