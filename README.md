# Tinkercad-Based Smart Fan Project

**Korea National Open University – Computer Science**
**Course:** Arduino (2025)
**Project Link:** [Tinkercad Smart Fan Simulation](https://www.tinkercad.com/things/fZCN4xplMaM-?sharecode=Oun6sho9MWKSrw86HVZ0y4fy0z2cc_yTPAnTAcPjr7k)

## Project Overview

This project implements a **smart fan system** using the Arduino simulator in Tinkercad. It aims to provide an intuitive, multi-functional fan with realistic simulation features that can be controlled via buttons or an IR remote.

## Key Features

- **Wind speed control:** 4-step adjustment (OFF, Level 1, 2, 3) via button or IR remote
- **Rotation toggle:** Enables/disables left-right sweep function through button or remote
- **Speed display:** Current fan speed shown on a 7-segment display
- **Rotation indicator:** LED signals whether the fan is rotating


## Circuit Components and Connections

| Component                    | Arduino Pin(s) | Purpose                                     |
|                          :-- |            :-- |                                         :-- |
| Arduino Uno R3               | —              | Main controller and power supply            |
| Push Buttons (2)             | D2, D3         | Speed adjustment, rotation toggle           |
| Servo Motor                  | D0             | Controls left-right swinging motion         |
| IR Receiver                  | D4             | IR remote input                             |
| DC Motor                     | D5 (PWM)       | Fan speed control via PWM                   |
| LED                          | D6             | Rotation status indicator                   |
| 7-Segment Display            | D7-D13         | Displays current speed step                 |
| Transistor, Diode, Resistors | —              | Power circuit, protection, current limiting |

## Functional Description \& Code Outline

- **Initialization (setup):** Set pin modes, attach interrupts for buttons, ensure outputs are off initially
- **Speed Control (fnModFanSpeed):** Cycles fan speed through OFF → 1 → 2 → 3 → OFF, sets PWM and updates display
- **Rotation Control (fnFanRotate):** Toggles rotation state, drives servo motor sweep (0°–180°), blinks LED when active
- **IR Remote Handling (remote):** Power toggle, speed increase/decrease, rotation toggle with debounce logic
- **Interrupt Service Routines:** Efficiently handle button presses with minimal delay and debounce


## IR Remote Button Mapping

| Button   | Function            |
|      :-- | :--                 |
| Power(0) | Toggle power ON/OFF |
| ≪ (4)   | Decrease wind speed |
| ≫ (6)   | Increase wind speed |
| ▶ (5)   | Toggle fan rotation |

## Simulation Results Summary

- Fan speed and rotation can be controlled via both physical buttons and IR remote
- Real-time speed feedback displayed on the 7-segment display
- DC motor speed accurately changes according to selected level
- Rotation LED correctly indicates fan swing status
- System properly resets and stops all outputs when powered off


## Conclusion

This project successfully demonstrates a versatile smart fan simulation combining multiple input/output devices on an Arduino platform in Tinkercad. It illustrates robust interrupt-based control, user feedback integration, and real-world application functionality with a clean circuit design and well-documented code.

Feel free to ask if you want me to format the code sections or expand on any specific part!

