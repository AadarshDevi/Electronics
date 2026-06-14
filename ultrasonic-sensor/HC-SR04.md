# HC-SR04 Ultrasonic Sensor

## Connection

| Sensor Pin | ESP32-WROOM-32UE Pin | Wire Color |
|:----------:|:--------------------:|:----------:|
|    GND     |         GND          |   Black    |
|    ECHO    |     Digital Pin 16   |   Orange   |
|    TRIG    |     Digital Pin 17   |   Yellow   |
|    VCC     |         5V           |     Red    |

## Code

1. Setup the pins: `echoPin` and `trigPin`
```c
#define echoPin 16 // input
#define trigPin 17 // output
```
2. input pin: `echoPin` and output pin: `trigPin`
```c
digitalWrite(echoPin, INPUT);
digitalWrite(trigPin, OUTPUT);
```
