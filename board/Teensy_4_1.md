# Teensy 4.1

## Setup

### Arduino IDE
1. Add Lib: File > Preferences > Additional Boards Manager URL:
   ```javascript
   https://www.pjrc.com/teensy/package_teensy_index.json
   ```
2. Add Board: Board Manager
   1. Search @ "Teensy"
   2. Board Name: Teensy (for Arduino IDE 2.0.4 or later)
   3. Version: 1.62.0
   4. Author: Paul Stoffregen

3. Setup Board:
   1. Tools > Board > Teensy (for Arduino IDE 2.0.4 or later) > Teensy 4.1
   2. Tools > CPU Speed > 600 MHz
   3. Tools > USB Type > Serial
   4. Tools > Port > COM**_X_** Serial (Teensy 4.1)

### CLion PlatformIO

## Upload Code

### Arduino IDE

1. Press Program Mode Button (Press and Hold)
2. Click Upload
