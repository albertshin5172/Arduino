Korea National Open University - Computer Science

Enrolled class - Arduino (2025)

Project Link : https://www.tinkercad.com/things/fZCN4xplMaM-?sharecode=Oun6sho9MWKSrw86HVZ0y4fy0z2cc_yTPAnTAcPjr7k 

Tinkercad-Based Smart Fan Project

1. Project Overview and Purpose
This project aims to design and simulate a smart fan system using Tinkercad’s Arduino simulator. The goal is to create a fan that can:

Adjust wind speed (3 steps + OFF) using a button or an IR remote.

Toggle rotation (left-right swing) functionality via button or IR remote.

Display the current speed step on a 7-segment display.

Indicate rotation status with an LED.

The system leverages both input devices (buttons, IR remote) and output devices (DC motor, servo motor, 7-segment display, LED) to solve a practical problem: providing an intuitive, multi-functional, and interactive fan system suitable for real-life usage and simulation environments.

2. Circuit Configuration
Main Components & Connections
Component	Arduino Pin	Purpose
Arduino Uno R3	–	Main controller and power supply
Breadboard	–	Circuit assembly
Push Button (x2)	D2 (interruptPin1)	Speed adjustment (left button)
D3 (interruptPin2)	Rotation toggle (right button)
Servo Motor	D0 (servoPin)	Left-right swing motion
IR Receiver	D4 (rotatePin)	Remote control input
DC Motor	D5 (motorPin, PWM)	Main fan speed control
LED	D6 (ledPin)	Rotation status indicator
7-Segment Display	D7 to D13 (segPin[i])	Speed level display
Transistor/Diode/Resistor	Power circuit	Power delivery, protection, current limiting
Block Diagram
Inputs: Buttons, IR Receiver

Processing: Arduino Uno R3 (digital, PWM, interrupt logic)

Outputs: DC Motor (fan), Servo Motor (rotation), 7-Segment Display (speed), LED (rotation status)

3. Function Description
Wind Speed Control
4 steps: 0 (OFF), 1, 2, 3

PWM Values: 0, 85, 170, 255 (proportional control)

Display: Current speed shown on 7-segment

Rotation Control
Servo Motor operates 0°–180° for wide Sweeping.

Rotation status LED blinks when active.

IR Remote Control
Power: ON/OFF toggle.

Wind speed: Increase (≫, button 6), decrease (≪, button 4).

Rotation toggle: (▶, button 5).

Manual Button Control (Interrupt-based)
Button 1 (D2): Change fan speed step (interrupt).

Button 2 (D3): Toggle rotation mode (interrupt).

4. Core Code & Logic Description
Initialization (setup())
Set pin modes for all devices and initialize peripherals.

Attach interrupts for both buttons.

Ensure all outputs start in the OFF or idle state.

Wind Speed Change (fnModFanSpeed())
Cycles through speed step 0→1→2→3→0.

Sets PWM value and 7-segment output accordingly.

Rotation State Toggle (fnFanRotate())
Changes the status variable for rotation.

Servo motor swing logic driven in the main loop when rotation is active.

IR Remote (remote())
Reads IR input, maps to function based on button code.

Handles debounce and ensures only appropriate commands execute based on power state.

System Power (togglePower())
Turns the fan ON/OFF.

Resets outputs and display when turned OFF.

Speed and Rotation Step Interrupts
ISR Functions: Debounced, minimal, update step variable and state.

Servo Motor Swing
When rotation is active, servo sweeps between 0° and 180° in steps.

Rotation indicator LED provides visual feedback.

5. Simulation & Results
Remote Button Functions
Button	Function
Power (0)	Toggle ON/OFF
≪ (4)	Decrease speed
≫ (6)	Increase speed
▶ (5)	Toggle fan rotation
Results Summary
Speed and Rotation can be controlled by both button and remote.

7-Segment accurately shows speed step (0–3).

DC motor speed changes as per selected step.

Rotation status LED correctly reflects current state.

System resets and all output devices stop when powered OFF.

6. Conclusion
This project successfully implemented a smart fan system within Tinkercad, simulating real-world interactions. It showcased effective integration of multiple input and output devices, interrupt-driven manual control, and user-friendly feedback. All requirements—creativity, functionality, well-commented code, and robust circuit design—were met.

7. Tinkercad Simulation Link
Smart Fan Tinkercad Project Link (public)

Note:

For code highlights, see the embedded comments and function breakdown in the source.

For detailed schematic and simulation visuals, refer to the provided Tinkercad link.
