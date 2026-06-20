# TB6612FNG Motor Driver

### Pinout

| Pin     | Description                                          |
|:--------|:-----------------------------------------------------|
| VM      | External Power Source                                |
| VCC     | 3.3V of Board                                        |
| GND     | Ground                                               |
| Aout1   | Motor A Power Output 1                               |
| Aout2   | Motor A Power Output 2                               |
| Bout1   | Motor B Power Output 1                               |
| Bout2   | Motor B Power Output 2                               |
| PWMA    | PWM Command for Motor A                              |
| INA2    | Input 2 Command for Motor A                          |
| INA1    | Input 1 Command for Motor A                          |
| STANDBY | Used to hookup a switch. Connected to 3.3V of Board. |
| INB1    | Input 1 Command for Motor B                          |
| INB2    | Input 2 Command for Motor B                          |
| PWMB    | PWM Command for Motor B                              |


### Connection

Base Connection for motor Controller

| Motor Controller | ESP32 WROVER Module | Other                     |
|:-----------------|:--------------------|:--------------------------|
| VM               | -                   | External Power Source     |
| VCC              | 3.3V                |                           |
| GND              | GND                 | External Power Source GND |
| STANDBY          | 3.3V                | External Switch           |

#### No PWM

| Motor Controller | ESP32-WROOM-32UE | ESP32 WROVER Module | Motor |
|:-----------------|:------|--------------|:------|
| PWM A/B          | 3v3 | 3.3V                |       |
| IN A/B 1         | GPIO21 | GPIO21         |       |
| IN A/B 2         | GPIO22 | GPIO22         |       |
| OUT A/B 1        | - | -                   | Wire  |
| OUT A/B 2        | - | -                   | Wire  |

#### PWM

| Motor Controller | ESP32-WROOM-32UE | ESP32 WROVER Module | Motor |
|:-----------------|:-------------|:-------|:------|
| PWM A/B          | GPIO23 (ADC) | GPIO23 (ADC)          |       |
| IN A/B 1         | GPIO21 | GPIO21         |       |
| IN A/B 2         | GPIO22 | GPIO22         |       |
| OUT A/B 1        | - | -                   | Wire  |
| OUT A/B 2        | - | -                   | Wire  |

### Programming

#### PWM

1. Motor A Pins
```c
// Motor A pins  
const int AIN1 = 21;          // motor pin 1 (Used for direction)
const int AIN2 = 22;          // motor pin 2 (Used for direction)
const int PWMA = 23;          // motor PWM pin
```

2. Max motor val
```c
const int maxMotorVal = 255;  // max speed
```

3. Set the pins to output
```c
pinMode(AIN1, OUTPUT);        // ouput because motor's rotation pin
pinMode(AIN2, OUTPUT);        // ouput because motor's rotation pin
pinMode(PWMA, OUTPUT);        // ouput because motor's pwm pin
```

4. Set motor speed
```c
int motorVal = 100;           // motor speed aka duty cycle
```

5. Map input value to output speed then set speed
```c  
// rotate a direction
digitalWrite(AIN1, HIGH);
digitalWrite(AIN2, LOW);

// stopping motor
digitalWrite(AIN1, HIGH);
digitalWrite(AIN2, LOW);

// rotate opposite direction
digitalWrite(AIN1, HIGH);
digitalWrite(AIN2, LOW);

// motor destroyed
digitalWrite(AIN1, HIGH);
digitalWrite(AIN2, LOW);
```

6. Set motor speed
```c
analogWrite(PWMA, motorVal);
```
