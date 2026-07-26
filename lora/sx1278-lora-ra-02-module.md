# SX1278 LoRa RA-02 Module (433MHz)

## Components
1. ESP32-WROOM-32UE
2. SX1278 LoRa RA-02 Module (433MHz)
3. Jumper Wires

## Connection(s)
| LoRa Module                    | ESP32 WROVER Module | 
|:-------------------------------|:--------------------|
| 3V3                            | 3V3                 |
| GND                            | GND                 |
| MISO (SPI Data Pin)            | MISO                |
| MOSI (SPI Data Pin)            | MOSI                |
| SCK  (SPI Data Pin)            | SCK                 | 
| DIO0                           | GPIO27              |    
| RST                            | GPIO26              |    
| NSS  (SPI Input Pin)           | GPIO5               |    

## Library Manager
1. LoRa by Sandeep Mistry

## Programming

1. Set LoRa SS/NSS, RST, DIO0 (Optional) Pins
```c
#define LORA_NSS_PIN 5 // slave select
#define LORA_RST_PIN 26 // reset
#define LORA_DIO0_PIN 27 // data pin

LoRa.setPins(LORA_NSS_PIN, LORA_RST_PIN, LORA_DIO0_PIN);
```

2. 

## Additional Info
aka Notes

## Projects
list of projects that use the sensor/ic

## Sources / Resources
1. [Interfacing Esp32 with LoRa using Arduino IDE](https://embeddedthere.com/esp32-lora-tutorial-using-arduino-ide/)
