# Teensy 4.1

## Pinout

<img width="632" height="685" alt="image" src="https://github.com/user-attachments/assets/cb3690c5-88c5-44e1-8a77-40cac9b4dfd7" />

## Setup

### Arduino IDE

#### Board Manager

1. File > Preferences > ***Additional boards manager URLs*** window button
2. Add JSON link
   ```javascript
   https://www.pjrc.com/teensy/package_teensy_index.json
   ```
3. Close and reopen Arduino IDE
4. Board Manager > Search @ "Teensy"
5. Install: Teensy (for Arduino IDE 2.0.4 or later) by Paul Stoffregen

#### Board Setup
1. Tools > Board > Teensy (for Arduino IDE 2.0.4 or later) > Teensy 4.1
2. Tools > Port > COM{X} Serial (Teensy 4.1)
3. Tools > CPU Speed > 600 MHz
4. Tools > USB Type > Serial

### CLion PlatformIO

### PlatformIO CLI

1. Create Folder: `My_PlatformIO_Project`
2. Go into folder: `cd My_PlatformIO_Project`
3. Create PlatformIO Project: `pio project init --board teensy41`
4. Create Git repo: `git init`
## Upload Code

### Arduino IDE

1. Choose program to upload
2. Press Program Mode Button (Press and Hold): Big white button in the center.
3. Click Upload button
## Additional Info

