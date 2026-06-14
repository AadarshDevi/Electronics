# HC-SR04 Ultrasonic Sensor

## Connection

| Sensor Pin | ESP32-WROOM-32UE Pin | Wire Color |
|:----------:|:--------------------:|:----------:|
|    GND     |         GND          |   Black    |
|    ECHO    |     Digital Pin 16   |   Orange   |
|    TRIG    |     Digital Pin 17   |   Yellow   |
|    VCC     |         5V           |     Red    |

## Library manager
1. Install library: **UltrasonicSensor** by **Giuseppe Martini**

## Code

1. Setup the pins: `echoPin` and `trigPin`
```c
#define echoPin 16 // input
#define trigPin 17 // output
```
2. Create UltrasonicSensor
```c
UltrasonicSensor ultrasonic(trigPin, echoPin);
```
3. Get Distance in centimeter(cm)
```c
int distance_in_cm = ultrasonic.distanceInCentimeters();
Serial.print("Distance (cm): ");
Serial.println(distance_in_cm);
```
4. Get Distance in millimeter (mm)
```c
int distance_in_mm = ultrasonic.distanceInMillimeters();
Serial.print("Distance (mm): ");
Serial.println(distance_in_mm);
```
5. Get Distance in microseconds (us)
```c
int distance_in_us = ultrasonic.distanceInMicroseconds();
Serial.print("Distance (us): ");
Serial.println(distance_in_us);
```

## Additional Info
1. I used an ESP32-WROOM-32UE and I needed to have Serial @ baudrate=115200 (ESP32 uses 115200 for sending diagnostic info to serial monitor)
2. Link to the [UltrasonicSensor Library](https://github.com/gmarty2000-ARDUINO/arduino-ULTRASONIC_SENSOR/tree/master) that helped me to understand the library
