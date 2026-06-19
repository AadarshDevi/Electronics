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

| Motor Controller | ESP32 WROVER Module | Motor |
|:-----------------|:--------------------|:------|
| PWM A/B          | 3.3V                |       |
| IN A/B 1         | Digital Pin         |       |
| IN A/B 2         | Digital Pin         |       |
| OUT A/B 1        | -                   | Wire  |
| OUT A/B 2        | -                   | Wire  |

#### PWM

| Motor Controller | ESP32 WROVER Module | Motor |
|:-----------------|:--------------------|:------|
| PWM A/B          | Analog Pin          |       |
| IN A/B 1         | Digital Pin         |       |
| IN A/B 2         | Digital Pin         |       |
| OUT A/B 1        | -                   | Wire  |
| OUT A/B 2        | -                   | Wire  |

##### Programming

1. PWM Motor A Pins
```c
const int AIN1 = 21;    //directional pin
const int AIN2 = 22;    //directional pin
const int PWMA = 23; //pwm (speed) pin 
// Setting duty cycle: 255 (2^8-1) is 100% speed
int dutyA = 100;  // ~40% of max speed
```

2. Set the pins to output
```c
pinMode(AIN1, OUTPUT);
pinMode(AIN2, OUTPUT);
pinMode(PWMA, OUTPUT);
```

3. max motor speed
```c
int maxMotorVal = 255;
```

4. map input vlue to output speed
```c
analogWrite(PWMA, motorVal);
```
