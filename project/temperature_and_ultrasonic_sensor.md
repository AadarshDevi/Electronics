# Temperature & Ultrasonic Sensors

## Aim
Use **Temperature sensor** to get the current temperature and give it to the **Ultrasonic sensor** for a better accurate distance.

## Components
1. Microcontroller (Mine: ESP32-WROOM-32UE)
2. HC-SR04 Ultrasonic Sensor
3. DHT11 Digital Temperature & Humidity Sensor

## Setup
Both tutorials below need to be completed because I do not want to repeat the same things.
1. [DHT11 Sensor Tutorial](https://github.com/AadarshDevi/Electronics/blob/master/humidity-temperature-sensor/DHT11.md#programming)
2. [HC-SR04 Sensor Tutorial](https://github.com/AadarshDevi/Electronics/blob/master/ultrasonic-sensor/HC-SR04.md#programming)

## Programming
1. Program the DHT11 Sensor
2. Program the HC-SR04 Sensor

### Basic
Taking the temperature from DHT11 and putting it into HC-SR04
```c

#include <DHT.h>
#include <DHT_U.h>
#include <UltrasonicSensor.h>

// pins & types
#define hcsr04EchoPin 16 // echo pin: input
#define hcsr04TrigPin 17 // trigger pin: output

#define dht11Pin 18 // dht pin
#define dhtType DHT11 // dht type

// objects
UltrasonicSensor ultrasonic(hcsr04TrigPin, hcsr04EchoPin);
DHT_Unified dht(dht11Pin, dhtType);

// vars
int delay_in_ms;
int temperature = 22; // Celsius
  

void setup() {

  Serial.begin(115200);
  while(!Serial) {}

  dht.begin();
  
  // get sensor info  
  sensor_t tempSensor;
  dht.temperature().getSensor(&tempSensor); // get temperature sensor;

  delay_in_ms = tempSensor.min_delay / 1000; // 1 Hz Read
}

void loop() {

  sensors_event_t tempEvent;
  dht.temperature().getEvent(&tempEvent);

    // read temp sensor
  if (!isnan(tempEvent.temperature)) {
    Serial.print("Temperature: ");
    Serial.println(tempEvent.temperature); // i can read sensor
    ultrasonic.setTemperature(temperature);
  } else {
    Serial.println("Unable to read Sensor: Temperature");
  }

  int distance_in_cm = ultrasonic.distanceInCentimeters();
  Serial.print("Distance (cm): ");
  Serial.println(distance_in_cm);

  delay(delay_in_ms);
}

```

### Medium
Take the temperature and check if it hasnt changed or is in the acceptable range. If it is in acceptable range, do not set values.
