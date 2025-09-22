# SHPE Robotics Showcase Project!

Welcome to SHPE Showcase project, where we will be wsing a live camera feed through Raspberry pi to remote control an RC Car!



# Overall System Layout:

Raspberry Pi 5 - Used for video streaming, connecting to gamepad, and the brains behind our project

Arduino Uno - Used for motor driver control instead of driver board for realtime editing (USB serial communcation)

Motor Driver - TBD

Steering Actuator - TBD (Either a servo or DC motor)

Camera - Pi Camera ORRRRRR USB 1080p webcam -> able to stream through Pi on Linux

Battery (Main power source) - TBD (Battery pack perchance a 2S LiPo (7.4V) depending on driver/motors)

Buck Converter - Powers PI by converting battery voltage to stable 5V

Game controller - Hopefully an XBOX controller

Breadboard - Size TBD


## POWER HIERARCHY:


Battery (Main Power Source)
  -> Buck Converter -> Raspberry Pi (Needs clean 5V) ~ 3-5A -> Arduino (through USB cable) ~500 mA
  
  -> Motor Driver (VM or 12V pins) *Connect VCC + GND to Arduino through breadboard*
  
  -> GND -> Conenct PI GND, Uno GND, Motor Driver GND, Buck Converter GND, Battery GND to common ground! Otherwise something's gonna get shorted asf.

## Current Estimate for now

Drive Motor ~ 3A

Steering    ~ 1 A

Pi 5        ~ 4 A

Extra       ~ 1 A

  ~ 9 Amp Peak

Starting on Raspberry PI:
## Quick Start (on a Pi)
```bash
# ONLY RUN ONCE PER PI
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# Run control loop (gamepad → serial → Arduino) (EVENTUALY)
python src/pi/pi_control.py

