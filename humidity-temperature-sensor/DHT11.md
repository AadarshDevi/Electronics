# DHT11 Temperature & Humidity Sensor

## Components
1. ESP32-WROOM-32UE
2. Jumper Wires
3. DHT11 Temperature & Humidity Sensor

## Connection

| DHT11 Pin |       ESP32 Pin      | Wire Color |
|:---------:|:--------------------:|:----------:|
|    GND    |         GND          |    Black   |
|    Data   |     Digital Pin 21   |    Green   |
|    VCC    |         5V           |    Red     |

## Library Manager
1. **DHT sensor library** by **Adafruit** (Install with dependencies)

## Programming

1. Include lib
```c
#include <DHT.h>
#include <DHT_U.h>
```
2. Set Sensor Pin & Type
```c
#define dht11Pin 18
#define dhtType DHT11
```
3. Create Sensor & get how many times the sensor gives data
```c
DHT_Unified dht(dht11Pin, dhtType); // create obj

sensor_t sensor; // sensor that will give the delay
delay_in_ms = humiditySensor.min_delay / 1000; // 1 Hz Read
```
4. Start the sensor (i think thats what this does)
```c
dht.begin();
```
5. Read temperature. It is in °C
```c
sensors_event_t tempEvent;

// can the program read the temp from the sensor
dht.temperature().getEvent(&tempEvent);

// read temp sensor
if (!isnan(tempEvent.temperature)) {

  // read sensor
  Serial.print("Temperature: ");
  Serial.println(tempEvent.temperature);
} else {

  // unable to read sensor
  Serial.println("Unable to read Sensor: Temperature");
}
```
6.
```c
sensors_event_t humidityEvent;

// can the program read the temp from the sensor
dht.humidity().getEvent(&humidityEvent);

// read humidity sensor
if (!isnan(humidityEvent.relative_humidity)) {

  // read sensor
  Serial.print("Humidity: ");
  Serial.println(humidityEvent.relative_humidity);
} else {

  // unable to read sensor
  Serial.println("Unable to read Sensor: Humidity");
}
```
7. DHT11 Sensor reads @ 1Hz (1 time per second)
```c
delay()
```

## Additional Info
1. [Library on Arduino's Website](https://docs.arduino.cc/libraries/dht-sensor-library/)
2. [GitHub Repo by Adafruit](https://github.com/adafruit/DHT-sensor-library)
3. [Learn about DHT11 (Adafruit)](https://learn.adafruit.com/dht)
4. [Pinout for DHT11](https://components101.com/sensors/dht11-temperature-sensor)
5. File > Examples > DHT sensor library > DHT_Unified_Sensor

## Projects
1. Use Temperature/Humidity Sensor to give UltrasonicSensor with better Temperature values [Temperature & Ultrasonic Sensors](https://github.com/AadarshDevi/Electronics/blob/master/project/temperature_and_ultrasonic_sensor.md)
