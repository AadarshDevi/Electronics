# HC-SR04 Ultrasonic Sensor

## Connection

| Sensor Pin | ESP32-WROOM-32UE Pin | Wire Color |
|:----------:|:--------------------:|:----------:|
|    GND     |         GND          |   Black    |
|    ECHO    |     Digital Pin 16   |   Orange   |
|    TRIG    |     Digital Pin 17   |   Yellow   |
|    VCC     |         5V           |     Red    |

## Library manager
1. Install library: UltrasonicSensor by Giuseppe Martini

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
Serial.println("Distance (cm): "+String(distance_in_cm));
```
4. Get Distance in millimeter (mm)
```c
int distance_in_mm = ultrasonic.distanceInMillimeters();
Serial.println("Distance (mm): "+String(distance_in_mm));
```
5. Get Distance in microseconds (us)
```c
int distance_in_us = ultrasonic.distanceInMicroseconds();
Serial.println("Distance (us): "+String(distance_in_us));
```
