# Motor Controller

## Sparkfun TB6612FNG Motor Driver

### Pinout

| Pin     | Description                                          |
|:--------|:-----------------------------------------------------|
| VM      | External Power Source                                |
| VCC     | 3.3V of Board                                        |
| GND     |                                                      |
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

#### No PWM

| Motor Controller   | ESP32 WROVER Module | Other                 |
|:-------------------|:--------------------|:----------------------|
| VM                 | -                   | External Power Source |
| VCC                | 3.3V                |                       |
| GND                |                     |                       |
| STANDBY            | 3.3V                | External Switch       |

| Motor Controller | ESP32 WROVER Module | Motor |
|:-----------------|:--------------------|:------|
| PWM A/B          | 3.3V                |       |
| IN A/B 1         | Digital Pin         |       |
| IN A/B 2         | Digital Pin         |       |
|                  |                     |       |
|                  |                     |       |
|                  |                     |       |

#### PWM