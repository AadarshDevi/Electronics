# Temperature & Ultrasonic Sensors

## Aim
Use **Temperature sensor** to get the current temperature and give it to the **Ultrasonic sensor** for a better accurate distance.

## Components
1. Microcontroller (Mine: ESP32-WROOM-32UE)
2. HC-SR04 Ultrasonic Sensor
3. DHT11 Digital Temperature & Humidity Sensor

## Connections

| HC-SR04 Pin |       ESP32 Pin      | Wire Color |
|:-----------:|:--------------------:|:----------:|
|     GND     |         GND          |   Black    |
|     ECHO    |     Digital Pin 16   |   Orange   |
|     TRIG    |     Digital Pin 17   |   Yellow   |
|     VCC     |         5V           |     Red    |


| DHT11 Pin |       ESP32 Pin      | Wire Color |
|:-----------:|:--------------------:|:----------:|
|     GND     |         GND          |   Black    |
|     ECHO    |     Digital Pin 16   |   Orange   |
|     VCC     |         5V           |     Red    |

