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

2. Set Sync Word (Comms Channel), Coding Rate 4 (Error Correction), Signal Bandwidth (), Spreading Factor ()
```c
LoRa.setSignalBandwidth(SIGNAL_BANDWIDTH);
LoRa.setSpreadingFactor(SPREAD_FACTOR);
LoRa.setCodingRate4(CODE_RATING_4);
LoRa.setSyncWord(SYNC_WORD);
```

3. Send Data
```c
LoRa.beginPacket(); // start data packet
LoRa.print("Count: "); // data
LoRa.print(String(count)); // data
LoRa.endPacket(); // close data packet and send it
```

4. Receive Data
```c
String data = ""; // var to hold data
int packetSize = LoRa.parsePacket(); // size of the packet = is there a packet? if no 0, if yes, give the packet size 

if (packetSize) { // if packet size is greater than 0 (0 bytes)

  // checks to see how many bytes are available
  // read every single byte
  while (LoRa.available()) {
    data += (char) LoRa.read();
  }
  data.trim();
  Serial.println("Packet: \"" + data + "\"");
}
```

## Sources / Resources
1. [Interfacing Esp32 with LoRa using Arduino IDE](https://embeddedthere.com/esp32-lora-tutorial-using-arduino-ide/)
2. [LoRa API](https://github.com/sandeepmistry/arduino-LoRa/blob/master/API.md)
